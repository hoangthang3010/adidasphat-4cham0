<template>
  <div>
    <!-- <img class="image custom flying" src="../assets/image.png" alt="" @click="click" :style="[checkgo1]"  style="-ms-touch-action: manipulation; touch-action: manipulation;">
    <audio id="yourAudioTag" controls style="display: none">
      <source src="../assets/tiengmo_2.mp3" type="audio/ogg">
      <source id="" src="../assets/tiengmo_2.mp3" type="audio/mpeg">
    </audio>
    <img class="image right" src="../assets/image2.png" alt="" @click="click2" style="-ms-touch-action: manipulation; touch-action: manipulation;">
    <audio id="yourAudioTag1" controls style="display: none">
      <source src="../assets/tiengchuongchua_3.mp3" type="audio/ogg">
      <source id="" src="../assets/tiengchuongchua_3.mp3" type="audio/mpeg">
    </audio> -->
    <div class="container">
      <div class="content-top">
        <div class="temperature">{{isOn ? temperature : ''}}</div>
        <img class="iharmonic" v-if="!isOn" src="../assets/dieuhoa-off.png"/>
        <img class="iharmonic" v-else src="../assets/dieuhoa.gif"/>
      </div>
      <div class="content-control">
        <div class="temperature" v-show="isOn">{{isOn ? temperature : ''}}</div>
        <input class="btn-control btn-on" type="button" :value="!isOn ? 'Bật' : 'Tắt'" @click="isOn = !isOn;">
        <div class="box-increase btn-control">
          <!-- <svg width="24" height="13" viewBox="0 0 240 130" style="top: 0; position: absolute; transform: translate(-50%, 0);"
              xmlns="http://www.w3.org/2000/svg"
               @click="temperature < 40 ? temperature++ : temperature">
            <polygon points="120,0 240,130 0,130"/>
          </svg> -->
          <input class="btn-control btn-increase" type="button" value="Tăng" @click="temperature < 30 ? temperature++ : temperature">
        </div>
        <div class="box-decrease btn-control">
          <input class="btn-decrease" type="button" value="Giảm" @click="temperature > 16 ? temperature-- : 16">
        </div>
        <img class="remote-control" src="../assets/remote-control.png"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      click1: true,
      temperature: 30,
      isOn: true
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
      // event.stopPropagation()
    },
    click2 (event) {
      document.getElementById('yourAudioTag1').currentTime = 0
      document.getElementById('yourAudioTag1').play()
      console.log(1234)
    }
  }
}
</script>

<style scoped lang="scss">
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
.content-top{
  position: relative;
  width: fit-content;
  margin: auto;
}
.temperature{
position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%);
font-size: 40px;
color: rgb(212, 212, 213);
font-weight: 500;
font-family: inherit;
/* border: 1px solid rgb(86, 86, 86); */
}
.content-control{
  margin-top: 300px !important;
  width: fit-content;
  height: fit-content;
  margin: auto;
  position: relative;
  .temperature{
    position: absolute;
    top: 60px;
    left: 55px;
    font-size: 22px;
    color: #2b2b2b;
    &::before{
      content: "*";
      position: absolute;
      font-size: 15px;
      top: 2px;
      left: 24px;
    }
    &::after{
      content: 'c';
      position: absolute;
      font-size: 13px;
      top: 3px;
      left: 30px;
    }
  }
}
.remote-control{
  height: 300px;
}
.btn-control{
  position: absolute;
}
.btn-on{
  top: 128px;
  left: 47px;
  width: 24px;
  height: 16px;
  opacity: 0;
}
.box-increase{
  top: 150px;
  left: 47px;
  width: 24px;
  height: 13px;
  &::after{
    position: absolute;
    content: "";
    top: -3px;
    left: 18px;
    width: 6px;
    height: 18px;
    transform: rotate(135deg);
  }
  &::before{
    position: absolute;
    content: "";
    top: -3px;
    left: 0px;
    width: 6px;
    height: 18px;
    -webkit-transform: rotate(135deg);
    transform: rotate(225deg);
  }
}
.box-decrease{
  top: 180px;
  left: 47px;
  width: 24px;
  height: 13px;
  &::after{
    position: absolute;
    content: "";
    top: -3px;
    left: 18px;
    width: 6px;
    height: 18px;
    transform: rotate(135deg);
  }
  &::before{
    position: absolute;
    content: "";
    top: 0px;
    left: 18px;
    width: 6px;
    height: 18px;
    -webkit-transform: rotate(135deg);
    transform: rotate(45deg);
  }
}
.btn-increase{
  width: 100%;
  height: 100%;
  position: relative;
  opacity: 0;
}
.btn-decrease{
  width: 100%;
  height: 100%;
  position: relative;
  opacity: 0;
}
</style>
