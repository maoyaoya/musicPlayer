<template>
  <div class="foot">
    <div class="control">
      <img class="pre" src="../../../assets/imgs/music_pre.png">
      <img class="play" @click="playMusic" src="../../../assets/imgs/music_play.png" :style="{display: !play ? 'inline-block' : 'none'}">
      <img class="play" @click="pauseMusic" src="../../../assets/imgs/music_stop.png" :style="{display: !play ? 'none' : 'inline-block'}">
      <img class="next" src="../../../assets/imgs/music_next.png" >
    </div>
    <div class="progress">
      <span>{{current}}</span>
      <vue-slider class="playprogress" ref="slider" v-bind="setting" style="display:inline-block;padding:15px 10px;" v-model="progress"></vue-slider>
      <span>{{end}}</span>
      <img class="volume" src="../../../assets/imgs/volume.png">
      <vue-slider class="volumeprogress" ref="slider2" v-bind="setting2" style="display:inline-block;padding:15px 10px;" v-model="volume"></vue-slider>
    </div>
  </div>
</template>

<script>
import VueSlider from 'vue-slider-component'
import Vue from 'vue'
export default {
  name: 'HomeFoot',
  components: {
    VueSlider,
  },
  props: {
    musics: Array
  },
  data() {
    return {
      app: '网易云音乐',
      setting: {
        width: 430,
        tooltip: false,
        dotSize: 13,
        processStyle: {
          'background-color': 'rgb(232,60,60)'
        },
        min: 0,
        max: 200,
        clickable: true,
        speed: 1.0
      },
      progress: 0,
      setting2: {
        width: 100,
        tooltip: 'hover',
        dotSize: 10,
        clickable: true,
        processStyle: {
          'background-color': 'rgb(232,60,60)'
        },
        max: 100,
        min: 0
      },
      volume: 100,
      play: false,
      current: '00:00',
      end: '00:00',
      update: '',
      drag: false,
      listShow: false
    }
  },
  methods: {
    playMusic: function () {
      if (!this.mp3Url) {
        return
      }
      this.update = setInterval(this.getCurrent, 1000 / 60)
      this.play = true
    },
    pauseMusic: function () {
      clearInterval(this.update)
      this.play = false
    }
  }
}
</script>

<style lang="stylus" scoped>
.foot
  width 100%
  height 50px
  box-sizing border-box
  background-color rgb(246, 246, 248)
  border 1px solid rgb(225, 225, 226)
  position relative
  padding-left 30px
  .control, .progress
    float left
    margin-left 20px
    .pre, .next
      width 32px
      height 32px
      cursor pointer
      border-radius 50%
      position relative
    .play
      width 36px
      height 36px
      border-radius 50%
      cursor pointer
      margin 6px 10px 7px
    .volume
      width 20px
      height 20px
      opacity 0.5
      position relative
      left 5px
      top -5px
    .playprogress, .volumeprogress
      position relative
      top 10px
    span
      position relative
      top -5px
</style>



