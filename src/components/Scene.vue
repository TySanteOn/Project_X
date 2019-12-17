<template>
  <div class="scene" ref="scene">
  </div>
</template>

<script>
import * as THREE from "three";

export default {
  name: 'Scene',
  mounted () {
    this.initThree();
  },
  methods: {
    initThree() {

      this.scene = new THREE.Scene();
      this.camera = new THREE.PerspectiveCamera( 75, window.innerWidth / window.innerHeight, 0.1, 1000 );

      this.renderer = new THREE.WebGLRenderer();
      this.renderer.setSize( window.innerWidth, window.innerHeight );
      document.body.appendChild( this.renderer.domElement );

      let geometry = new THREE.BoxGeometry( 1, 1, 1 );
      let material = new THREE.MeshPhongMaterial( { color: 0xF2634A } );
      this.cube = new THREE.Mesh( geometry, material );
      this.scene.add( this.cube );

      this.camera.position.z = 5;

      const color = 0xFFFFFF;
      const intensity = 2;
      const light = new THREE.DirectionalLight(color, intensity);
      light.position.set(-3, 3, 4);
      this.scene.add(light);

      this.animate()

    },
    animate() {
      this.cube.rotation.x += 0.01;
      this.cube.rotation.y += 0.01;
      this.renderer.render( this.scene, this.camera );
      requestAnimationFrame( this.animate );

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .scene {
    width: 100vw;
    height: 100vh;
  }
</style>
