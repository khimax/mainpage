<script setup>
import { onBeforeUnmount, onMounted } from 'vue'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import TrackCard from '@/components/TrackCard.vue'
import tracks from '@/data/tracks.json'

const latestTrackBackgroundColor = tracks[0].backgroundColor
const latestTrackColor = tracks[0].textColor

const ZONE_SELECTOR = '[data-zone]'

const intersectingZones = new Map()

let observer = null

function setPageBackgroundColor(color) {
  if (color) {
    document.documentElement.style.setProperty('--page-bg', color)
  }
}

function pickActiveColor() {
  const viewportCenter = window.innerHeight / 2
  let activeColor = null
  let closestDistance = Infinity

  for (const [element, color] of intersectingZones) {
    const rect = element.getBoundingClientRect()
    const distance = Math.abs((rect.top + rect.bottom) / 2 - viewportCenter)
    if (distance < closestDistance) {
      closestDistance = distance
      activeColor = color
    }
  }

  setPageBackgroundColor(activeColor ?? latestTrackBackgroundColor)
}

setPageBackgroundColor(latestTrackBackgroundColor)

onMounted(() => {
  const zones = document.querySelectorAll(ZONE_SELECTOR)

  observer = new IntersectionObserver(
    (entries) => {
      for (const entry of entries) {
        const color = entry.target.style.backgroundColor
        if (entry.isIntersecting && color) {
          intersectingZones.set(entry.target, color)
        } else {
          intersectingZones.delete(entry.target)
        }
      }
      pickActiveColor()
    },
    { rootMargin: '-40% 0px -40% 0px' },
  )

  for (const zone of zones) {
    observer.observe(zone)
  }

  window.addEventListener('resize', pickActiveColor)
})

onBeforeUnmount(() => {
  observer?.disconnect()
  observer = null
  window.removeEventListener('resize', pickActiveColor)
})
</script>

<template>
<Header
:textColor="latestTrackColor"
:backgroundColor="latestTrackBackgroundColor"
/>
<TrackCard
  v-for="(track, index) in tracks"
  :key="track.title"
  :track="track"
  :isLatest="index === 0"
/>
<Footer/>
</template>

<style scoped>
#latest {
  scroll-margin-top: 100px;
}
</style>
