<template lang="html">
  <div class="playingNow">
    <div class="title">
      <p class="clearFix">
        <span class="playHot">正在热映</span>
        <a href="#" class="aHref">全部正在热映»</a>
        <a href="#" class="aHref">即将上映»</a>
        <ul class="floatR">
          <li>
            <span><i>{{index}}</i>/<i>10</i></span>
          </li>
          <li>
            <a href="javascript:;" class="prevBtn btn">&lt;</a>
          </li>
          <li>
            <a href="javascript:;" class="nextBtn btn">&gt;</a>
          </li>
        </ul>
      </p>
    </div>
    <div class="swiper">
      <swipers @activeIndex="parentIndex"></swipers>
    </div>
  </div>
</template>

<script>
import swipers from './swiper.vue'
export default {
  data () {
    return {
      index: 1
    }
  },
  components: {
    swipers
  },
  methods: {
    parentIndex (data) {
      this.index = data
    }
  }
}
</script>

<style lang="less" scoped>
.playingNow {
    .title {
        border-bottom: 1px solid #eaeaea;
        line-height: 2.5;
        padding: 20px 0 0;
        .playHot {
            color: #111;
            margin-right: 15px;
        }
        .aHref {
            font-size: 13px;
            color: #666699;
            padding: 2px 3px;
            margin-right: 10px;
            &:hover {
                color: #fff;
                background: #666699;
            }
        }
        .floatR{
          float: right;
          padding-top: 5px;
          li{
            float: left;
            font-size: 13px;
            margin-left: 10px;
            .btn{
              background: rgb(111, 128, 242);
              padding: 2px 5px;
              border-radius: 50%;
              color:#fff;
            }
          }
        }

    }
    .swiper{
      width: 100%;
      height:270px;
      padding-top:18px;
    }
}
</style>
