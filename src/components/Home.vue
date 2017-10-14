<template>
  <video poster="../assets/home/concert.jpg" id="bgvid" playsinline autoplay muted loop>
    <!-- WCAG general accessibility recommendation is that media such as background video play through only once. Loop turned on for the purposes of illustration; if removed, the end of the video will fade in the same way created by pressing the "Pause" button  -->
    <source src="../assets/home/concert.webm" type="video/webm">
    <source src="../assets/home/concert.mp4" type="video/mp4">
  </video>
</template>

<script>
  export default {
    name: 'Home',
    data () {
      return {
        msg: 'This is Home'
      }
    }
  }
</script>

<style lang="scss" scoped>
  video {
    position: fixed;
    top: 50%;
    left: 50%;
    min-width: 100%;
    min-height: 100%;
    width: auto;
    height: auto;
    z-index: -100;
    transform: translateX(-50%) translateY(-50%);
    background: url('../assets/home/concert.jpg') no-repeat;
    background-size: cover;
    transition: 1s opacity;
  }

</style>
