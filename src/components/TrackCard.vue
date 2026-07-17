<script setup>
defineProps({
  track: {
    type: Object,
    required: true
  },
  isLatest: {
    type: Boolean,
    default: false
  }
})
</script>

<template>
  <div class="track-card" :id="isLatest ? 'latest' : undefined" :style="{ backgroundColor: track.backgroundColor }">
    <div class="container">
      <div class="track-header">
        <p class="title" :style="{color: track.backgroundColor, backgroundColor: track.textColor}">{{ track.title }}</p>
        <p class="collab" v-if="track.isCollab" :style="{color: track.textColor}">collab with <span class="collabers" :style="{color: track.altColor}">{{ track.collabers.join(', ') }}</span></p>
        <p class="release" v-else :style="{color: track.textColor}">{{ track.type }} release</p>
      </div>
      <div class="info" :style="{color: track.textColor}">
        <p>Released on {{ track.releaseDate }}</p>
      </div>
    </div>
    <img
      v-if="track.artwork"
      class="artwork"
      :src="track.artwork"
      :alt="`Artwork for ${track.title}`"
    />
    <div class="listen">
      <a :href="track.releaseLink" :style="{color: track.textColor}" >LISTEN LISTEN LISTEN LISTEN LISTEN</a>
      <a :href="track.releaseLink" :style="{color: track.textColor}" >LISTEN LISTEN LISTEN LISTEN LISTEN</a>
      <a :href="track.releaseLink" :style="{color: track.textColor}" >LISTEN LISTEN LISTEN LISTEN LISTEN</a>
    </div>
  </div>
</template>

<style scoped>

.listen a {
  display: block;
  width: 100%;
  font-size: 5.5cqw;
  white-space: nowrap;
  overflow: hidden;
  font-weight: bold;
}

.track-header{
  text-align: left;
}

.title {
  display: inline;
  box-decoration-break: clone;
  -webkit-box-decoration-break: clone;
  padding: 4px 8px;
  line-height: 1.5;
}

.track-card {
  padding: clamp(16px, 3vw, 32px);
  border-radius: clamp(6px, 1vw, 8px);
  width: clamp(280px, 50vw, 500px);
  margin-bottom: clamp(12px, 2vw, 16px);
  container-type: inline-size;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

p {
	text-align: left;
	margin: 4px 0;
  font-weight: bold;
  font-size: clamp(1rem, 2vw, 1.4rem);
}

.collab, 
.release {
  font-style:italic;
}

.collabers{
  text-decoration:underline;
  font-style:normal;
}

.artwork {
	width: 100%;
	margin-top: 16px;
	border-radius: 8px;
}

.info p {
  font-size: clamp(0.6rem, 1vw, 0.8rem);
}

</style>