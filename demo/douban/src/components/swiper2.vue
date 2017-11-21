<template>
<div class="">
  <swiper class="" :options="swiperOption" :not-next-tick="notNextTick" ref="mySwiper">
    <!-- slides -->
    <swiper-slide>
      <ul class="clearFix">
        <li v-for="(data, index) in data">
          <div class="oneMovieBox" @mouseenter="showThisDetial(index)" >
            <img :src="data.img" alt="海报">
            <p class="scoreP"><span>{{data.title}}</span> <span>{{data.score}}</span> </p>
          </div>
          <div class="detailPop" v-if="data.showDetial" @mouseleave="showThisDetial(index)">
            <div class="movieDetail">
              <h3><span>{{data.title}}</span> <span>{{data.englishTitle}}</span> <span>{{data.year}}</span> </h3>
              <p><span>scoreStar</span><span>{{data.score}}</span><span>({{data.disscusNum}}人评价)</span> </p>
              <p><span>{{data.time}}</span><span>{{data.country}}</span> </p>
              <p>导演 {{data.author}}</p>
              <p>主演 {{data.actors}}</p>
            </div>
          </div>
        </li>
      </ul>
    </swiper-slide>
    <swiper-slide>
      <ul class="clearFix">

      </ul>
    </swiper-slide>
    <swiper-slide>I'm Slide 3</swiper-slide>
    <swiper-slide>I'm Slide 4</swiper-slide>
    <swiper-slide>I'm Slide 5</swiper-slide>

  </swiper>
  <div class="actionBtn">
    <div class="swiper2PrevBtn" slot="button-prev">&lt;</div>
    <div class="swiper-pagination" slot="pagination"></div>
    <div class="swiper2NextBtn" slot="button-next">&gt;</div>
  </div>
</div>
</template>

<script>
require('swiper/dist/css/swiper.css')
// swiper options example:
export default {
  name: 'carrousel',
  data() {
    return {
      data: [{
          title: '正义联盟',
          englishTitle: 'justice league',
          year: '2017',
          score: 6.9,
          scoreStar: '-14px',
          disscusNum: 114,
          time: '47分钟',
          country: '美国',
          author: '斯皮尔伯格',
          actors: '安吉丽娜朱莉/小罗伯特/扎克伯格',
          img: 'https://img3.doubanio.com/view/photo/s_ratio_poster/public/p2504027804.webp',
          showDetial: false
        },
        {
          year: '2017',
          title: '正义联盟',
          englishTitle: 'justice league',
          score: 6.9,
          scoreStar: '-14px',
          disscusNum: 114,
          time: '47分钟',
          country: '美国',
          author: '斯皮尔伯格',
          actors: '安吉丽娜朱莉/小罗伯特/扎克伯格',
          img: 'https://img3.doubanio.com/view/photo/s_ratio_poster/public/p2504027804.webp',
          showDetial: false
        }, {
          year: '2017',
          title: '正义联盟',
          englishTitle: 'justice league',
          score: 6.9,
          scoreStar: '-14px',
          disscusNum: 114,
          time: '47分钟',
          country: '美国',
          author: '斯皮尔伯格',
          actors: '安吉丽娜朱莉/小罗伯特/扎克伯格',
          img: 'https://img3.doubanio.com/view/photo/s_ratio_poster/public/p2504027804.webp',
          showDetial: false
        }
      ],
      // NotNextTick is a component's own property, and if notNextTick is set to true, the component will not instantiate the swiper through NextTick, which means you can get the swiper object the first time (if you need to use the get swiper object to do what Things, then this property must be true)
      // notNextTick是一个组件自有属性，如果notNextTick设置为true，组件则不会通过NextTick来实例化swiper，也就意味着你可以在第一时间获取到swiper对象，假如你需要刚加载遍使用获取swiper对象来做什么事，那么这个属性一定要是true
      notNextTick: true,
      swiperOption: {
        autoplay: 3000,
        direction: 'horizontal',
        grabCursor: true,
        setWrapperSize: true,
        autoHeight: true,
        pagination: '.swiper-pagination',
        prevButton: '.prevBtn',
        nextButton: '.nextBtn',
        scrollbar: '',
        loop: true,
        mousewheelControl: false,
        observeParents: true,
        debugger: true,
        paginationClickable: true,
        prevButton: '.swiper2PrevBtn',
        nextButton: '.swiper2NextBtn',
        onTransitionStart: swiper => {
          this.activeIndex = swiper.activeIndex
          this.$emit("activeIndex", swiper.activeIndex)
        }
      }
    }
  },
  // you can find current swiper instance object like this, while the notNextTick property value must be true
  // 如果你需要得到当前的swiper对象来做一些事情，你可以像下面这样定义一个方法属性来获取当前的swiper对象，同时notNextTick必须为true
  computed: {
    swiper() {
      return this.$refs.mySwiper.swiper
    }
  },
  mounted() {
    this.swiper.slideTo(1, 1000, false)
    //this.addData()
  },
  methods: {
    showThisDetial(index) {
      this.data[index].showDetial = !this.data[index].showDetial;
      // this.data[index].showDetial = true;
    },
    addData() {
      for (var i = 0; i < 7; i++) {
        this.data.push(this.data[i]);
      }
    }
  }
}
</script>


<style lang="less">
.swiper-slide {
    ul {
      min-height:385px;
        li {
            float: left;
            margin: 0 7px;
            position: relative;
        }
    }
}
.actionBtn{
  position:relative;
  height:30px;
  display:flex;
  justify-content:center;
  margin-top:15px;
  >div{
    margin:0 10px;
  }
  .swiper-pagination-bullet{
    margin:0 5px;
  }
  .swiper-pagination{
    position:static;
  }
  .swiper2NextBtn,.swiper2PrevBtn{
    color:#fff;
    background:#37a;
    border-radius:20px;
    width:20px;
    height:20px;
    text-align:center;
    line-height:20px;
  }
}

.oneMovieBox {
    text-align: center;
    width: 120px;
    img {
        width: 115px;
    }
    .scoreP {
        text-align: center;
        span {
            font-size: 13px;
            &:first-child {
                color: #37a;
            }
            &:last-child {
                color: #e09015;
            }
        }
        .scoreStar {
            width: 70px;
            height: 15px;
            display: block;
            background: url("../assets/ic_rating_s@2x.png") no-repeat;
            /*
        0,14,28,42,56,70,84
      */
            background-position: 0 0;

            background-size: 100%;
            margin-right: 15px;
        }
    }
    .chooseSeatP {
        .chooseSeat {
            font-size: 12px;
            color: #fff;
            background: #268dcd;
            padding: 4px 15px;
        }
        line-height: 1.5;
        text-align: center;
    }

}
.detailPop{
  position: absolute;
  top: 0;
  left: 0;
    z-index: 20;
    padding-left:130px;
  .movieDetail {


      background: #fff;
      padding: 10px;
      min-width: 200px;
      border: 1px solid #e3e3e3;
      font-size: 12px;
      h3 {
          font-size: 15px;
      }
      p {
          margin: 10px 0;
          span {
              margin-right: 5px;
          }
      }

  }
}

</style>
