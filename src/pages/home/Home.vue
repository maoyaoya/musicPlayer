<template>
  <div>
    <home-header></home-header>
    <home-list></home-list>
    <home-slide ></home-slide>
    <home-test 
      class="slide"
      :list="setData()" 
      :width="800"
      :height="260"
      ></home-test>
  </div>
</template>

<script>
import HomeHeader from './components/header'
import HomeList from './components/list'
import HomeSlide from './components/slide'
import SlidePicture from './components/slidePicture'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeList,
    HomeSlide,
    SlidePicture
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
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
.slide
  margin-left 180px
</style>
