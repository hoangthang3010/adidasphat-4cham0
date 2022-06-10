<template>
  <div>
    <img src="../assets/image.png" alt="" @click="click">
    <audio id="yourAudioTag" controls style="display: none">
      <source src="../assets/ting.mp3" type="audio/ogg">
      <source id="" src="../assets/ting.mp3" type="audio/mpeg">
    </audio>
    <img src="../assets/image2.png" alt="" @click="click2">
    <audio id="yourAudioTag1" controls style="display: none">
      <source src="../assets/tiengchuongchua_3.mp3" type="audio/ogg">
      <source id="" src="../assets/tiengchuongchua_3.mp3" type="audio/mpeg">
    </audio>
  </div>
</template>

<script>
export default {
  data () {
    return {
      // click: true;
    }
  },
  methods: {
    click () {
      document.getElementById('yourAudioTag').currentTime = 0
      document.getElementById('yourAudioTag').play()
      console.log(1234)
    },
    click2 () {
      document.getElementById('yourAudioTag1').currentTime = 0
      document.getElementById('yourAudioTag1').play()
      console.log(1234)
    }
  }
}
</script>

<style scoped>

</style>
