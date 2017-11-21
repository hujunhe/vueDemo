<template lang="html">
  <div class="view1">
    <topBar></topBar>
    <searchBox></searchBox>
    <div class="mainBody">
      <div class="leftPart">
        <playing></playing>
        <img src="https://img3.doubanio.com/view/dale-online/dale_ad/public/4f759233cb7b0a3.jpg" alt="" width="100%" height="112">
        <recentMovie></recentMovie>
        <recentTv></recentTv>
      </div>
      <div class="rightPart">

      </div>
    </div>
  </div>

</template>

<script>
import topBar from '../components/topBar.vue'
import searchBox from '../components/searchBox.vue'
import playing from '../components/playing.vue'
import recentMovie from '../components/recentMovie'
import recentTv from '../components/recentTv.vue'
export default {
  components: {
    topBar,
    searchBox,
    playing,
    recentMovie,
    recentTv
  }
}
</script>

<style lang="less">
.mainBody{
  padding:10px;
}
</style>
