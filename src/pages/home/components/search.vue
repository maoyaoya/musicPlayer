<template>
  <div class="search">
    <input placeholder="搜索音乐、视频、歌词、电台"/><i class="search-icon"></i>
  </div>
</template>

<script>
export default {
  name: 'search',

}
</script>

<style lang="stylus" scoped>
.search
  position relative
  input
    width 220px
    height 24px
    border none
    border-radius 10px
    outline none
    font-size 12px
    line-height 1
    padding 0 30px 0 10px
    box-sizing border-box
    background-color rgba(0, 0, 0, 0.4)
  i
    position absolute
    display block
    width 20px
    height 20px
    background-size cover
    background-image url('../../../assets/imgs/search.png')
    left 195px
    top 15px
    cursor pointer
</style>
