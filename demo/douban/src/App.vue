<template>
  <div id="app">
    <view_index></view_index>
  </div>
</template>

<script>
import view_index from './views/view1.vue'
export default {
  name: 'app',
  components: {
    view_index
  }
}
</script>

<style lang="less">
.clearFix{
  &:after{
    visibility: hidden;
    display: block;
    font-size: 0;
    content: " ";
    clear: both;
    height: 0;
  }
}
ul,li,html,body,p{
  padding: 0;
  margin: 0;
}
a{
  text-decoration: none;
}
li{
  list-style-type: none;
}
.mainBody{
  display: flex;
  width: 1000px;
  margin: 0 auto;
  .leftPart{
    width: 675px;
  }
  .right{
    width: 300px;
  }
}
</style>
