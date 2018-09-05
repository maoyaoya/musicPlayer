<template>
<div class="slide">
   <div class="nav">
     <ul class="nav-list">
       <li>个性推荐</li>
        <li>歌单</li>
        <li>主播电台</li>
        <li>排行榜</li>
        <li>歌手</li>
        <li>最新音乐</li>
     </ul>
   </div>
</div>
</template>

<script>
export default {
  name: 'HomeSlide',
  props: {
    imgs: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl'

.slide
  overflow hidden
  .nav
    width 90%
    margin 0 auto
    text-align center
    height 50px
    line-height 50px
    border-bottom 1px solid #ccc
    .nav-list
      width 90%
      margin 0 auto
      li
        float left
        width 74px
        font-size 16px
        margin 0 7px
        cursor pointer
      li:first-child
        border-bottom 2px solid $bgColor
        color $bgColor
      li:hover
        color $bgColor
</style>

