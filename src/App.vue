<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import TrackCard from '@/components/TrackCard.vue'
import tracks from '@/data/tracks.json'

const latestTrackBackgroundColor = tracks[0].backgroundColor
const latestTrackColor = tracks[0].textColor
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
