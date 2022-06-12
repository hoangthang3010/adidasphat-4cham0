<template>
  <div>
    <img class="image custom flying" src="../assets/image.png" alt="" @click="click" :style="[checkgo1]">
    <audio id="yourAudioTag" controls style="display: none">
      <source src="../assets/ting.mp3" type="audio/ogg">
      <source id="" src="../assets/ting.mp3" type="audio/mpeg">
    </audio>
    <img class="image right" src="../assets/image2.png" alt="" @click="click2">
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
      click1: true,
    }
  },
  computed: {
    checkgo1() {
      return this.click1 ? {cursor: 'url(' + require('../assets/go1.png') + '), auto'} : ''
    }
  },
  methods: {
    click (event) {
      document.getElementById('yourAudioTag').currentTime = 0
      document.getElementById('yourAudioTag').play()
      console.log(1234)
      event.stopPropagation()
      event.preventDefault();
    },
    click2 (event) {
      document.getElementById('yourAudioTag1').currentTime = 0
      document.getElementById('yourAudioTag1').play()
      console.log(1234)
      event.preventDefault();
    }
  }
}
</script>

<style scoped>
.image{
  height: 150px;
  width: 150px;
  margin: 0 40px;
}
.flying{
  /* cursor: url('https://res.cloudinary.com/dvkugaw3b/image/upload/v1641562028/cursor_ad12rf.png'), auto; */
  cursor: url('~@/assets/go1.png'), auto;
  /* background-image: url('../ '); */
}
</style>
