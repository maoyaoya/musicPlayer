<template>
  <div class="list">
    <ul>
      <li><span>推荐</span></li>
      <li><img class="icon" src="../../../assets/imgs/music.png">发现音乐</li>
      <li><img class="icon" src="../../../assets/imgs/fm.png">私人FM</li>
      <li><img class="icon" src="../../../assets/imgs/mv.png">MV</li>
      <li><img class="icon" src="../../../assets/imgs/friend.png">朋友</li>
      <li><span>我的音乐</span></li>
      <li><img class="icon" src="../../../assets/imgs/local_music.png">本地音乐</li>
      <li><img class="icon" src="../../../assets/imgs/download.png">下载管理</li>
      <li><span>创建的歌单</span></li>
      <li><img class="icon" src="../../../assets/imgs/heart.png">我喜欢的音乐</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeList'
}
</script>

<style lang="stylus" scoped>
.list
  background-color rgb(245, 245, 247)
  width 20%
  height 100%
  border-right 1px solid #ccc
  li
    height 30px
    line-height 30px
    font-size 12px
    span
      margin-left 10px
    .icon
      width 18px
      height 18px
      margin 10px 10px 15px 20px
</style>
