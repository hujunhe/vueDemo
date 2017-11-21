<template lang="html">
  <div class="mainBar">
    <div class="searchBox clearFix">
      <img src="https://img3.doubanio.com/dae/accounts/resources/321e246/movie/assets/lg_movie_a12_2.png" alt="豆瓣电影">
      <div class="searchBoxInput">
        <input type="text" name="" value="">
        <a href="#"></a>
      </div>
    </div>
    <div class="hotNav">
      <ul class="clearFix">
        <li v-for="data in hotNavList">
          <a :href="data.href">{{data.name}}</a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      hotNavList: [{
        name: '影讯&购票',
        href: 'https://movie.douban.com/cinema/nowplaying/'
      }, {
        name: '选电影',
        href: 'https://movie.douban.com/cinema/nowplaying/'
      }, {
        name: '电视剧',
        href: 'https://movie.douban.com/cinema/nowplaying/'
      }, {
        name: '排行榜',
        href: 'https://movie.douban.com/cinema/nowplaying/'
      }, {
        name: '分类',
        href: 'https://movie.douban.com/cinema/nowplaying/'
      }, {
        name: '影评',
        href: 'https://movie.douban.com/cinema/nowplaying/'
      }, {
        name: '2016年度榜单',
        href: 'https://movie.douban.com/cinema/nowplaying/'
      }, {
        name: '2016观影报告',
        href: 'https://movie.douban.com/cinema/nowplaying/'
      }]
    }
  }
}
</script>

<style lang="less">
.mainBar{
  @minWidth:1040px;
  background: #e3ebec;
  .searchBox{
    width: @minWidth;
    margin: 0 auto;
    padding: 10px;
    border-bottom: 1px solid lightgrey;
    img{
      float: left;
      display: block;
      margin: 10px 20px 10px 10px;
    }
    .searchBoxInput{
      @width: 470px;
      float: left;
      width: @width;
      padding-top: 5px;
      input{
        width: @width - 50;
        float: left;
        height: 24px;
      }
      a{
        float: left;
        background: url(//img3.doubanio.com/dae/accounts/resources/321e246/movie/assets/nav_mv_bg.png?s=1) no-repeat 0 -40px;
        padding: 30px 35px 0 0;
        border-radius: 0 5px 5px 0;
      }
    }
  }
  .hotNav{
    width: @minWidth;
    margin: 0 auto;
    padding: 0 10px;
    ul{
      li{
        float: left;
        margin-right: 20px;
        line-height: 40px;
        a{
          color: #27a;
          padding: 4px 4px;
          &:hover{
            background: #27a;
            color: #fff;
          }
        }

      }
    }
  }
}
</style>
