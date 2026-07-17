<script setup>
defineProps({
  textColor: {
    type: String,
    required: true
  },
  backgroundColor: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="header-card" :style="{backgroundColor}">
    <div class="header">
        <img
        class="logo"
        src="/images/artworks/nymphaea.jpeg"
        alt="`khimax profile picture`"
        />
        <div class ="header-text">
          <div class="header-title" :style="{color: textColor}">
            <h1>khimax</h1>
          </div>
          <div class="divider" :style="{ borderTop: '3px dotted ' + textColor }"></div>
          <div class="header-info" :style="{color: textColor}">
            <p>Music artist, game developer.</p>
          </div>
        </div>
    </div>
    <div class="info">
      <a href="https://t.me/khimax_music"  class="button" :style="{ border: '1px solid ' + textColor, color: textColor}">
        <span>TELEGRAM</span>
        <div class="buttonLogo">
          <svg :fill="textColor" height="20" viewBox="0 0 20 20" width="20" xmlns="http://www.w3.org/2000/svg"><path d="m1.77404283 9.58769086c4.67714245-1.99564845 7.79596997-3.31130205 9.35648257-3.9469608 4.4555806-1.81493491 5.381412-2.13020854 5.984856-2.14061906.1327219-.0022897.4294781.02992311.6217044.18267827.162312.12898346.2069705.30322179.2283411.42551228.0213705.12229049.047982.40087134.0268279.61854631-.2414495 2.48450744-1.2861975 8.51375174-1.817706 11.29644264-.2249011 1.1774608-.6709749 1.4294697-1.0996928 1.4681058-.9317032.0839651-1.6359598-.4602232-2.5383599-1.0395344-1.412078-.9065075-1.9311138-1.1506648-3.30178003-2.0352487-1.58404193-1.0222898-.71982554-1.5573792.18291533-2.4756292.23625159-.2403103 4.3705401-3.98382431 4.4499945-4.31554914.0099371-.04148774-.12607-.45629906-.2198814-.53795815s-.2322689-.05373486-.3321837-.03152647c-.1416262.03147972-2.397439 1.49167812-6.76743852 4.38059516-.64030496.4305972-1.22027332.6403987-1.73990507.6294043-.5728523-.0121204-1.67479033-.3172064-2.49396798-.5779863-1.00475474-.3198572-1.37564449-.4704946-1.30610794-1.013711.03621894-.2829407.29151946-.57846124.76590154-.88656154z" stroke-width="1"/></svg>
        </div>
      </a>
      <a href="https://boosty.to/khimax" class="button" :style="{ border: '1px solid ' + textColor, color: textColor}">
        <span>BOOSTY</span>
        <div class="buttonLogo">
          <svg :fill="textColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" width="20"><path d="M2.661 14.337 6.801 0h6.362L11.88 4.444l-0.038 0.077 -3.378 11.733h3.15c-1.321 3.289 -2.35 5.867 -3.086 7.733 -5.816 -0.063 -7.442 -4.228 -6.02 -9.155M8.554 24l7.67 -11.035h-3.25l2.83 -7.073c4.852 0.508 7.137 4.33 5.791 8.952C20.16 19.81 14.344 24 8.68 24h-0.127z" stroke-width="1"></path>
          </svg>
        </div>
      </a>
      <a href="https://khimax.itch.io/" class="button" :style="{ border: '1px solid ' + textColor, color: textColor}">
        <span>ITCH.IO</span>
        <div class="buttonLogo">
          <svg :fill="textColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" width="20"><path d="M3.13 1.338C2.08 1.96.02 4.328 0 4.95v1.03c0 1.303 1.22 2.45 2.325 2.45 1.33 0 2.436-1.102 2.436-2.41 0 1.308 1.07 2.41 2.4 2.41 1.328 0 2.362-1.102 2.362-2.41 0 1.308 1.137 2.41 2.466 2.41h.024c1.33 0 2.466-1.102 2.466-2.41 0 1.308 1.034 2.41 2.363 2.41 1.33 0 2.4-1.102 2.4-2.41 0 1.308 1.106 2.41 2.435 2.41C22.78 8.43 24 7.282 24 5.98V4.95c-.02-.62-2.082-2.99-3.13-3.612-3.253-.114-5.508-.134-8.87-.133-3.362 0-7.945.053-8.87.133zm6.376 6.477a2.74 2.74 0 0 1-.468.602c-.5.49-1.19.795-1.947.795a2.786 2.786 0 0 1-1.95-.795c-.182-.178-.32-.37-.446-.59-.127.222-.303.412-.486.59a2.788 2.788 0 0 1-1.95.795c-.092 0-.187-.025-.264-.052-.107 1.113-.152 2.176-.168 2.95v.005l-.006 1.167c.02 2.334-.23 7.564 1.03 8.85 1.952.454 5.545.662 9.15.663 3.605 0 7.198-.21 9.15-.664 1.26-1.284 1.01-6.514 1.03-8.848l-.006-1.167v-.004c-.016-.775-.06-1.838-.168-2.95-.077.026-.172.052-.263.052a2.788 2.788 0 0 1-1.95-.795c-.184-.178-.36-.368-.486-.59-.127.22-.265.412-.447.59a2.786 2.786 0 0 1-1.95.794c-.76 0-1.446-.303-1.948-.793a2.74 2.74 0 0 1-.468-.602 2.738 2.738 0 0 1-.463.602 2.787 2.787 0 0 1-1.95.794h-.16a2.787 2.787 0 0 1-1.95-.793 2.738 2.738 0 0 1-.464-.602zm-2.004 2.59v.002c.795.002 1.5 0 2.373.953.687-.072 1.406-.108 2.125-.107.72 0 1.438.035 2.125.107.873-.953 1.578-.95 2.372-.953.376 0 1.876 0 2.92 2.934l1.123 4.028c.832 2.995-.266 3.068-1.636 3.07-2.03-.075-3.156-1.55-3.156-3.025-1.124.184-2.436.276-3.748.277-1.312 0-2.624-.093-3.748-.277 0 1.475-1.125 2.95-3.156 3.026-1.37-.004-2.468-.077-1.636-3.072l1.122-4.027c1.045-2.934 2.545-2.934 2.92-2.934zM12 12.714c-.002.002-2.14 1.964-2.523 2.662l1.4-.056v1.22c0 .056.56.033 1.123.007.562.026 1.124.05 1.124-.008v-1.22l1.4.055C14.138 14.677 12 12.713 12 12.713z" stroke-width="1"></path>
          </svg>
        </div>
      </a>
      <a href="#latest" class="button" :style="{ border: '1px solid ' + textColor, color: textColor}">
        <span>LATEST RELEASE</span>
        <div class="buttonLogo">
          <svg :fill="textColor" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" width="20"><path d="M 13 3 C 11.895 3 11 3.895 11 5 L 11 8 L 11 14.541016 A 4 4 0 0 0 9 14 A 4 4 0 0 0 5 18 A 4 4 0 0 0 9 22 A 4 4 0 0 0 13 18 L 13 8 L 16.5 8 C 17.881 8 19 6.881 19 5.5 C 19 4.119 17.881 3 16.5 3 L 13 3 z" stroke-width="1"></path>
          </svg>
        </div>
      </a>
    </div>
  </div>
</template>

<style scoped>
.header-card {
  padding: clamp(16px, 3vw, 32px);
  border-radius: clamp(6px, 1vw, 8px);
  width: clamp(280px, 50vw, 500px);
  margin-bottom: clamp(12px, 2vw, 16px);
}

.logo {
  width: 50%;
	border-radius: 8px;
	background-color: #1a1a2e;
  aspect-ratio: 1 / 1;
  object-fit: cover;
}

.header {
  display: flex;
  width: 100%;
  margin-bottom: 8px;
}

.header-text {
  width: 50%;
  display: flex;
  flex-direction: column;
}

.header-title,
.header-info {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.divider {
  width: 80%;
  margin: 0 auto;
}

.button {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 8px;
  padding: 16px;
  margin-bottom: 8px;

  text-decoration: none;
  font-weight: bold;

  transition: transform 0.2s ease;
}

.button:hover {
  transform: scale(1.03);
}

.button .buttonLogo {
  display: flex;
  align-items: center;
}

</style>