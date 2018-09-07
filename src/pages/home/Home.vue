<template>
  <div>
    <home-header></home-header>
      <home-list></home-list>
    <div class="scroll">
      <home-slide ></home-slide>
      <slide-picture 
        :list="setData()" 
        :width="800"
        :height="200"
        ></slide-picture>
        <home-album :musics="musics"></home-album>
    </div>
    <home-foot :musics="musics"></home-foot>
  </div>
</template>

<script>
import HomeHeader from './components/header'
import HomeList from './components/list'
import HomeSlide from './components/slide'
import SlidePicture from './components/slidePicture'
import HomeAlbum from './components/album'
import HomeFoot from './components/footer'
import axios from 'axios'
const API_PROXY = 'https://bird.ioliu.cn/v1/?url='
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeList,
    HomeSlide,
    SlidePicture,
    HomeAlbum,
    HomeFoot
  },
  data() {
    return {
      musics: []
    }
  },
  methods: {
    setData() {
      let list = [];
      for (let i = 1; i <= 9; i++) {
        list.push({
          title: i,
          src: '../../../../static/img/1-' + i + '.jpg'
        })
      }
      return list;
    },
    getHomeInfo() {
      var _this = this;
      axios.get(API_PROXY + 'http://music.163.com/api/playlist/detail?id=19723756').then(function (res) {
        _this.musics = res.data.result.tracks;
        console.log(_this.musics);
      }, function (error) {
        console.log(error)
      })
    }
  },
  mounted() {
    this.getHomeInfo();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
.scroll::-webkit-scrollbar
  width 4px
.scroll::-webkit-scrollbar-thumb
  border-radius 5px
  -webkit-box-shadow inset 0 0 5px rgba(0, 0, 0, 0.2)
  background rgba(0, 0, 0, 0.2)
.scroll
  height 500px
  overflow-y auto
  overflow-x hidden
</style>
