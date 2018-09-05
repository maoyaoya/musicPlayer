<template>
  <div class="header">
    <dl>
      <dd class="logo">
        <router-link to="/"><img src="../../../assets/imgs/logo2.jpg"></router-link>
      </dd>
      <dd class="control">
        <img @click="$router.go(-1)" src="../../../assets/imgs/pre.png">
        <img @click="$router.go(1)"  src="../../../assets/imgs/next.png">
     </dd>
     <dd>
       <search></search>
     </dd>
     <dd>
       <img class="preson-img" src="static/img/head.jpg">
       <i class="text">猫妖</i>
     </dd>
     <dd>
       <ul class="list">
        <li class="iconfont">&#xe6e0;</li>
        <li class="iconfont">&#xe647;</li>
        <li class="iconfont">&#xe61a;</li>
        <li class="line"></li>
        <li class="iconfont">&#xe624;</li>
        <li class="iconfont">&#xe66b;</li>
        <li class="iconfont">&#xe625;</li>
       </ul>
     </dd>
    </dl>
  </div>
</template>

<script>
import search from './search'
export default {
  name: 'HomeHeader',
  components: {
    search,
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'

dd
  float left
  height 50px
  line-height 50px
  box-sizing border-box
.header
  background-color $bgColor
  height 50px
  width 100%
  position relative
  .logo
    width 190px
  .control
    width 65px
    img
      height 18px
      width 22px
      border 1px solid rgb(168, 40, 40)
      cursor pointer
      border-radius 2px
      color rgba(0, 0, 0, 0.3)
      display block
      float left
      margin-top 25%
      padding 0 1px
  .preson-img
    float left
    width 30px
    height 30px
    border-radius 50%
    margin-left 100px
    margin-top 10px
  .text
    font-size 14px
    color rgba(255, 255, 255, 0.8)
    margin-left 10px
  .list
    position absolute
    right 10px
    color rgba(255, 255, 255, 0.6)
    .line
      width 1px
      height 20px
      background-color rgba(0, 0, 0, 0.4)
      margin 15px 0
  .list li
    float left
    margin-right 10px
    font-size 16px
    cursor pointer
  .list li:hover
    color white
  .list li:nth-child(5)
    margin-left 10px
</style>

