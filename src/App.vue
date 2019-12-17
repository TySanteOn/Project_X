<template>
  <div>
    <!-- <Scene /> -->
    <Gsap />
  </div>
</template>

<script>
// import Scene from './components/Scene.vue'
import Gsap from './components/Gsap.vue'

export default {
  name: 'app',
  components: {
    Gsap,
    // Scene
  },
}
</script>

<style>
html {
  font-size: 62.5%;
}

body {
  font-size: 100%;
  margin: 0;
}

/* canvas {
  width: 100%;
  height: 100%;
} */

p {
  margin: 0;
  font-size: 1.6rem;
}
</style>
