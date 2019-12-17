<template> 
  <div ref="box" class="box"></div>
</template>

<script>
  import { TimelineLite, Back } from 'gsap'
  
  export default {
    name: 'Gsap',
    data() {
      return {
        timeline: null,
      }
    },
    mounted () {
      const { box } = this.$refs 
      this.timeline = new TimelineLite({
        onComplete: () => this.timeline.restart()
      })
      this.animate(box) 
    },
    methods: {
      animate(box) {
        this.timeline.to(box, 1, {
          x: 200,
          rotation: 90,
          ease: Back.easeInOut,
        })
        
        this.timeline.to(box, 0.5, {
          background: 'green'
        }, '-=0.5')
        
        this.timeline.to(box, 1, {
          x: 0,
          background: 'green',
          ease: Back.easeInOut,
        });
        

        // requestAnimationFrame( this.animate );
      },
    }
  }
</script>

<style> 
.box { 
  height: 60px; 
  width: 60px; 
  background: red; 
  margin: 20px;
}
</style>