<template>
  <canvas class="background"></canvas>
</template>

<script>
import Particles from "particlesjs";
export default {
  data() {
    return {
      particles: null
    };
  },
  mounted() {
    let opt = Object.assign(
      {
        // normal options
        selector: ".background"
      },
      this.getResponsive1()
    );

    this.particles = Particles.init(opt);
  },
  methods: {
    getResponsive1() {
      return {
        color: "#75A5B7",
        maxParticles: 100,
        connectParticles: true,
        responsive: [
          {
            breakpoint: 768,
            options: {
              maxParticles: 80
            }
          },
          {
            breakpoint: 375,
            options: {
              maxParticles: 50
            }
          }
        ]
      };
    },
    getResponsive2() {
      return {
        maxParticles: 1050,
        // connectParticles: true,
        color: "#cccccc",
        responsive: [
          {
            breakpoint: 768,
            options: {
              maxParticles: 400,
              color: "#ff00ff",
              connectParticles: true
            }
          },
          {
            breakpoint: 425,
            options: {
              maxParticles: 100,
              connectParticles: true
            }
          }
        ]
      };
    },

    pause() {
      particles.pauseAnimation();
    },
    resume() {
      particles.resumeAnimation();
    }
  }
};
</script>
 
<style lang='scss' scoped>
.background {
  background: url("/images/bg1.jpg") no-repeat;
  background-size: 100% 100%;
  width: 100%;
  height: calc(100vh);

  position: absolute;
  display: block;
  top: 0;
  left: 0;
  z-index: 0;
}
</style>
