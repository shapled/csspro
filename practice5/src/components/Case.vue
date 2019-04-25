<template>
  <div class="cases">
    <div class="container">
      <div class="info"
        :class="{'active': infoIsVisible === true}"
        v-observe-visibility="{
          callback: infoVisibilityChanged,
          throttle: 300
        }">
        <h1 class="title">服务案例</h1>
        <p class="description">Best quality team</p>
      </div>
      <div class="content"
        :class="{'active': swiperIsVisible === true}"
        v-observe-visibility="{
          callback: swiperVisibilityChanged,
          throttle: 300
        }">
        <swiper class="swiper-wrap" :options="swiperOptions">
          <swiper-slide>
            <h3>暖男90后蚂蚁人，陪您把家搬完</h3>
            <p>在蚂蚁搬家的队伍中间，有一位特别优秀的90后，入职2年就被任命为搬运大组长，大家都亲切地称呼他：小老虎。</p>
            <div class="case-image">
              <img src="http://www.chinaant.net:6061/File/getFile/Article/993335717830590464">
            </div>
          </swiper-slide>
          <swiper-slide>
            <h3>搬家中遇见这样的服务，超赞！</h3>
            <p>如果您想选择一家拎包就能搬家的公司，那么我们公司是个不错的选择；如果您想拥有优质的搬家服务，那么我们公司是个不错的选择。</p>
            <div class="case-image">
              <img src="http://www.chinaant.net:6061/File/getFile/Article/992565583859941376">
            </div>
          </swiper-slide>
          <swiper-slide>
            <h3>确认过价格，认准蚂蚁人</h3>
            <p>每位客户选择蚂蚁搬家都是一种缘分，在搬家公司云集的时代，客户们的选择就是对我们服务质量和工作的最高认可。</p>
            <div class="case-image">
              <img src="http://www.chinaant.net:6061/File/getFile/Article/991865974862905344">
            </div>
          </swiper-slide>
          <swiper-slide>
            <h3>石家庄搬家：这家公司很靠谱</h3>
            <p>蚂蚁搬家石家庄搬家分公司成立于2003年，至今为止已经有15年的历史。蚂蚁搬家公司在石家庄的第一个客户，终身免费享受搬家服务</p>
            <div class="case-image">
              <img src="http://www.chinaant.net:6061/File/getFile/Article/976626873800851456">
            </div>
          </swiper-slide>
        </swiper>
        <i class="case-swiper-button-prev el-icon-arrow-left" slot="button-prev"></i>
        <i class="case-swiper-button-next el-icon-arrow-right" slot="button-next"></i>
      </div>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: "Case",
  components: {
    swiper,
    swiperSlide
  },
  data() {
    return {
      infoIsVisible: false,
      swiperIsVisible: false,
      swiperOptions: {
        autoplay: true,
        loop: true,
        slidesPerView: 3,
        spaceBetween: 55,
        slideActiveClass : 'case-swiper-slide-active',
        navigation: {
          nextEl: '.case-swiper-button-next',
          prevEl: '.case-swiper-button-prev',
        }
      }
    }
  },
  methods: {
    infoVisibilityChanged(isVisible, entry) {
      if(isVisible) {
        this.infoIsVisible = isVisible;
      }
    },
    swiperVisibilityChanged(isVisible, entry) {
      if(isVisible) {
        this.swiperIsVisible = isVisible;
      }
    }
  }
}
</script>

<style lang="postcss" scoped>
$selectDuration : 0.2s;

.cases {
  background: url(http://www.chinaant.net/resources/img/bg2@2x.png) no-repeat;
  background-size: 100% auto;
}

.container {
  padding-top: 60px;
  padding-bottom: 80px;
}

.info {
  width: 100%;
  text-align: center;
  margin-bottom: 20px;
  opacity: 0;

  &.active {
    opacity: 1;
    animation: fadeInUp 1.5s;
  }
  
  .title {
    font-size: 36px;
    font-weight: 500;
    color: white;
  }

  .description {
    font-size: 14px;
    margin-top: 10px;
    color: #d8d8d8;
  }
}

.content {
  position: relative;
  opacity: 0;

  &.active {
    opacity: 1;
    animation: zoomIn 0.8s;
  }

  .case-swiper-button-prev {
    width: 40px;
    height: 40px;
    line-height: 40px;
    text-align: center;
    font-size: 20px;
    background: white;
    opacity: 0.5;
    border-radius: 20px;
    position: absolute;
    top: 50%;
    left: -50px;
    transform: translate(0, -50%);
    transition: opacity $selectDuration ease-out;

    &:hover {
      opacity: 1;
      cursor: pointer;
    }

    &:focus {
      outline: none;
    }
  }

  .case-swiper-button-next {
    width: 40px;
    height: 40px;
    line-height: 40px;
    text-align: center;
    font-size: 20px;
    background: white;
    opacity: 0.5;
    border-radius: 20px;
    position: absolute;
    top: 50%;
    right: -50px;
    transform: translate(0, -50%);
    transition: opacity $selectDuration ease-out;

    &:hover {
      opacity: 1;
      cursor: pointer;
    }

    &:focus {
      outline: none;
    }
  }

  .swiper-wrap {
    padding: 50px 0px 20px 20px;
  }
}

.swiper-slide {
  background: white;
  padding: 20px;
  border-radius: 10px;
  height: 350px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  opacity: 0.7;
  transition: transform $selectDuration ease-out, opacity $selectDuration ease-out;

  h3 {
    color: #337ab7;
    font-size: 17px;
    font-weight: bold;
    line-height: 3em;
  }

  p {
    color: gray;
    font-size: 14px;
    line-height: 3.5em;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  .case-image {
    width: 100%;
    height: 170px;

    img {
      display: block;
      margin: 0 auto;
      width: 100%;
      height: 170px;
    }
  }

  &.case-swiper-slide-active {
    transform: scale(1.1, 1.1);
    opacity: 1;

    .case-image {
      height: 200px;
    }
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translate3d(0, 100%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

@keyframes zoomIn {
  from {
    opacity: 0;
    transform: scale3d(0.3, 0.3, 0.3);
  }

  50% {
    opacity: 1;
    transform: scale3d(1.1, 1.1, 1.1);
  }

  80% {
    transform: scale3d(0.95, 0.95, 0.95);
  }
}
</style>
