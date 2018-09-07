<template>
<div class="find">
  <div class="album">
    <div class="recommend">
      <div class="left">推荐歌单</div>
      <div class="right">更多<span class="iconfont icon-youjiantou"></span></div>
    </div>
    <div class="list">
      <div class="pic-list" v-for="(music,index) in setImgs()" :key="index">
          <img :src="music.src" style="width:130px;height:130px">
          <i class="test">{{music.title}}</i>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'HomeAlbum',
  props: {
    musics: Array
  },
  methods: {
    setImgs() {
      let list = [];
      for (var i = 1; i <= 8; i++) {
        list.push({
          title: '那些藏在回忆的记忆' + i,
          src: '../../../../static/img/' + i + '.jpg'
        })
      }
      return list;
    }
  }
}
</script>

<style lang="stylus" scoped>
.find
  height 200px
  .album
    width 90%
    margin 0 auto
    .recommend
      height 30px
      border-bottom 1px solid #eee
      .left
        float left
        font-size 18px
        line-height 30px
        margin 0 10px
      .right
        float right
        font-size 12px
        line-height 30px
        margin 0 10px
        span
          font-size 12px
    .list
      position relative
      .pic-list
        float left
        width 25%
        text-align center
        margin 20px 0
        .test
          display block
          margin-top 10px
</style>


