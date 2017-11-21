<template lang="html">
  <div class="recentMovie">
    <div class="title">
      <span class="recentHot">最近热门电影</span>
      <ul>
        <li>热门</li>
        <li>最新</li>
        <li>豆瓣高分</li>
        <li>冷门佳片</li>
        <li>华语</li>
        <li>欧美</li>
        <li>韩国</li>
        <li>日本</li>
      </ul>
    </div>
    <div class="movieBox">
      <swiper2></swiper2>
    </div>
  </div>
</template>

<script>
import swiper2 from './swiper2.vue'
export default {
  components: {
    swiper2
  }
}
</script>

<style lang="less">
.recentMovie{
  margin-top:20px;
  .title{
    margin-bottom:20px;
    .recentHot{
      float:left;
      margin-right:20px;
    }
    ul{
      display:flex;
      flex-direction:row;
      justify-content:space-between;
      padding-top:3px;
      li{
        font-size:13px;
        flex:1;
        text-align:center;
        color:#9B9B9B;
      }
    }
  }
  .movieBox{
    padding-bottom:40px;
  }
}
</style>
