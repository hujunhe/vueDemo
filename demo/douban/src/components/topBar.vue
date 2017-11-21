<template lang="html">
  <div class="topBar clearFix">
    <ul class="leftPart clearFix">
      <li>
        <a href="javascript:;">豆瓣</a>
      </li>
      <li>
        <a href="javascript:;">读书</a>
      </li>
      <li>
        <a href="javascript:;">电影</a>
      </li>
      <li>
        <a href="javascript:;">音乐</a>
      </li>
      <li>
        <a href="javascript:;">同城</a>
      </li>
      <li>
        <a href="javascript:;">小组</a>
      </li>
      <li>
        <a href="javascript:;">阅读</a>
      </li>
      <li>
        <a href="javascript:;">FM</a>
      </li>
      <li>
        <a href="javascript:;">时间</a>
      </li>
      <li>
        <a href="javascript:;">东西</a>
      </li>
      <li>
        <a href="javascript:;">市集</a>
      </li>
      <li>
        <a href="javascript:;">更多</a>
      </li>
    </ul>
    <ul class="rightPart clearFix">
      <li>
        <a href="#" @mouseenter="showDownLoadStatus = !showDownLoadStatus">下载客户端</a>
      </li>
      <li>
        <a href="#">登陆</a>
      </li>
      <li>
        <a href="#">注册</a>
      </li>
      <div class="urlPic" @mouseleave="showDownLoadStatus = !showDownLoadStatus" v-show="showDownLoadStatus">
        <img src="https://img3.doubanio.com/dae/accounts/resources/321e246/shire/assets/nav_doubanapp_6.png" alt="豆瓣ICON">
        <p class="title">豆瓣</p>
        <p class="solgan">我们的精神角落</p>
        <img src="https://img3.doubanio.com/dae/accounts/resources/321e246/shire/assets/nav_doubanapp_6_qrcode.png" alt="">
        <p class="phoneHref"><a href="#">iphone</a>·<a href="#">Android</a>  </p>
      </div>
    </ul>

  </div>
</template>

<script>
export default {
  data () {
    return {
      showDownLoadStatus: false
    }
  },
  method: {

  }
}
</script>

<style lang="less">
.topBar {
    @height: 28px;
    padding: 0 10px;
    height: @height;
    background: #545652;
    a {
        color: #d5d5d5;
        font-size: @height/2;
        &:hover {
            color: #fff;
        }
    }
    ul {
        &.leftPart {
            float: left;
        }
        &.rightPart {
            float: right;
            position: relative;
            .urlPic {
                position: absolute;
                top: @height + 2px;
                right: 0;
                width: 211px;
                padding: 50px 20px 30px;
                background: #fff;
                border: solid 1px #d5d5d5;
                border-top: none;
                text-align: center;
                .phoneHref {
                    a {
                        color: #37a;
                        margin: 0 5px;
                    }
                }
                .title {
                    font-size: 24px;
                    margin: 10px 0 5px;
                }
                .solgan {
                    font-size: 13px;
                    margin-bottom: 20px;
                }
            }
        }
        li {
            float: left;
            line-height: @height;
            margin: 0 10px;
        }
    }
}
</style>
