<template>
<swiper class="" :options="swiperOption" :not-next-tick="notNextTick" ref="mySwiper">
  <!-- slides -->
  <swiper-slide>
    <ul class="clearFix">
      <li v-for="(data, index) in data">
        <div class="oneMovieBox" @mouseenter="showThisDetial(index)" @mouseleave="showThisDetial(index)">
          <img :src="data.img" alt="海报">
          <p>嘉年华</p>
          <p class="scoreP clearFix"><span class="scoreStar"></span><span>{{data.score}}</span> </p>
          <p class="chooseSeatP"><a href="javascript:;" class="chooseSeat">选座购票</a> </p>
        </div>
        <div class="movieDetail" v-if="data.showDetial">
          <h3><span>{{data.title}}</span> <span>{{data.englishTitle}}</span> <span>{{data.year}}</span> </h3>
          <p><span>scoreStar</span><span>{{data.score}}</span><span>({{data.disscusNum}}人评价)</span> </p>
          <p><span>{{data.time}}</span><span>{{data.country}}</span> </p>
          <p>导演 {{data.author}}</p>
          <p>主演 {{data.actors}}</p>
        </div>
      </li>
    </ul>
  </swiper-slide>
  <swiper-slide>
    <ul class="clearFix">
      <li>
        <div class="oneMovieBox">
          <img src="https://img1.doubanio.com/view/photo/s_ratio_poster/public/p2503644828.webp" alt="海报">
          <p>嘉年华</p>
          <p class="scoreP clearFix"><span class="scoreStar"></span><span>7.1</span> </p>
        </div>
      </li>
      <li>
        <div class="oneMovieBox">
          <img src="https://img1.doubanio.com/view/photo/s_ratio_poster/public/p2503644828.webp" alt="海报">
          <p>嘉年华</p>
          <p class="scoreP clearFix"><span class="scoreStar"></span><span>7.1</span> </p>
        </div>
      </li>
      <li>
        <div class="oneMovieBox">
          <img src="https://img1.doubanio.com/view/photo/s_ratio_poster/public/p2503644828.webp" alt="海报">
          <p>嘉年华</p>
          <p class="scoreP clearFix"><span class="scoreStar"></span><span>7.1</span> </p>
        </div>
      </li>
      <li>
        <div class="oneMovieBox">
          <img src="https://img1.doubanio.com/view/photo/s_ratio_poster/public/p2503644828.webp" alt="海报">
          <p>嘉年华</p>
          <p class="scoreP clearFix"><span class="scoreStar"></span><span>7.1</span> </p>
        </div>
      </li>
      <li>
        <div class="oneMovieBox">
          <img src="https://img1.doubanio.com/view/photo/s_ratio_poster/public/p2503644828.webp" alt="海报">
          <p>嘉年华</p>
          <p class="scoreP clearFix"><span class="scoreStar"></span><span>7.1</span> </p>
        </div>
      </li>
    </ul>
  </swiper-slide>
  <swiper-slide>I'm Slide 3</swiper-slide>
  <swiper-slide>I'm Slide 4</swiper-slide>
  <swiper-slide>I'm Slide 5</swiper-slide>
  <swiper-slide>I'm Slide 6</swiper-slide>
  <swiper-slide>I'm Slide 7</swiper-slide>
  <swiper-slide>I'm Slide 8</swiper-slide>
  <swiper-slide>I'm Slide 9</swiper-slide>
  <swiper-slide>I'm Slide 10</swiper-slide>
</swiper>
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
        paginationClickable: false,
        prevButton: '.prevBtn',
        nextButton: '.nextBtn',
        scrollbar: '',
        loop: true,
        mousewheelControl: false,
        observeParents: true,
        debugger: true,
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
  mounted () {
    this.swiper.slideTo(1, 1000, false)
  },
  methods: {
    showThisDetial(index) {
      this.data[index].showDetial = !this.data[index].showDetial;
    }
  }
}
</script>


<style lang="less" scoped>
.swiper-slide {
    ul {
        li {
            float: left;
            margin: 0 7px;
            position: relative;
        }
    }
}
.oneMovieBox {
    text-align: center;
    width: 120px;
    img {
        width: 115px;
    }
    .scoreP {
        span {
            float: left;
            font-size: 13px;
            color: #e09015;
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
.movieDetail {
    position: absolute;
    top: 0;
    left: 130px;
    z-index: 20;
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
</style>
