<template>
  <div class="sub-brands">
    <div class="container">
      <div class="info"
        :class="{'active': infoIsVisible === true}"
        v-observe-visibility="{
          callback: infoVisibilityChanged,
          throttle: 300
        }">
        <h1 class="title">子属品牌</h1>
        <p class="description">The child is a brand</p>
      </div>
      <swiper class="swiper-wrap" :options="swiperOptions">
        <swiper-slide>
          <div class="brand-logo">
            <img src="http://chinaant.net:6061/File/getFile/CompanyLogo/909674487195107328">
          </div>
          <h3>熊猫搬</h3>
          <p>熊猫搬是蚂蚁搬家旗下精品搬家品牌，对精心挑选的优质客户提供一站式高品质搬家服务，托管式订制搬家，搬出地收纳打包，搬入地整体还原。</p>
          <div class="go">
            <i class="el-icon-sort-down"></i>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="brand-logo">
            <img src="http://chinaant.net:6061/File/getFile/CompanyLogo/909680073047539712">
          </div>
          <h3>好久搬</h3>
          <p>好久搬是蚂蚁搬家旗下小件快搬品牌，提供小件快搬、家具拆装、上门取货等一系列优质服务，现在预约，马上出发，提供专业、迅捷、安全、省心又省时的搬送。</p>
          <div class="go">
            <i class="el-icon-sort-down"></i>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="brand-logo">
            <img src="http://www.chinaant.net:6061/File/getFile/CompanyLogo/1065800505466290176">
          </div>
          <h3>72房客</h3>
          <p>成都七十二房客是蚂蚁搬家品牌旗下租房产品，为客户提供最优质的房源以及成都地区最优质的民宿，给您想要的家，让您不再为租房而发愁，居家旅游的好帮手！</p>
          <div class="go">
            <i class="el-icon-sort-down"></i>
          </div>
        </swiper-slide>
        <swiper-slide>
          <div class="brand-logo">
            <img src="http://www.chinaant.net:6061/File/getFile/CompanyLogo/1065801041087299584">
          </div>
          <h3>得仓堆店</h3>
          <p>得仓堆店为蚂蚁搬家品牌旗下品牌之一，主要负责食堂供应、生产物质、基建维修、服务装饰、网络软件、业务材料、货品纸箱、广告印刷、办公家具等业务。</p>
          <div class="go">
            <i class="el-icon-sort-down"></i>
          </div>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: "SubBrand",
  components: {
    swiper,
    swiperSlide
  },
  data() {
    return {
      infoIsVisible: false,
      swiperOptions: {
        autoplay: true,
        loop: true,
        slidesPerView: 3,
        spaceBetween: 20,
        // noSwiping : true,
        // noSwipingClass : 'swiper-wrap',
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      }
    }
  },
  methods: {
    infoVisibilityChanged(isVisible, entry) {
      if(isVisible) {
        this.infoIsVisible = isVisible;
      }
    }
  }
}
</script>

<style lang="postcss" scoped>
$selectDuration : 0.2s;

.sub-brands {
  background: #F4F4F4;
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
    color: #676767;
  }

  .description {
    font-size: 14px;
    margin-top: 10px;
    color: #d8d8d8;
  }
}

.swiper-wrap {
  padding: 50px 10px 70px 10px;
  
  /deep/.swiper-pagination-bullet {
    background: #007AFF;
    width: 10px;
    height: 10px;
    margin: 0 5px;
    opacity: 0.5;

    &:focus {
      outline: none;
    }
  }

  /deep/.swiper-pagination-bullet-active {
    opacity: 1;
  }
}

.swiper-slide {
  background: white;
  padding: 20px;
  border-radius: 10px;
  transition: transform $selectDuration ease-out, box-shadow $selectDuration ease-out;

  .brand-logo {
    margin: 20px 0;
    height: 90px;

    img {
      display: block;
      margin: 0 auto;
      height: 90px;
      max-width: 100%;
    }

    &::after {
      content: "";
      display: block;
      height: 1px;
      width: 100%;
      background: #ECECEC;
      margin-top: 10px;
    }
  }

  h3 {
    font-size: 15px;
    font-weight: bold;
    color: #777777;
    line-height: 2em;
  }

  p {
    font-size: 12px;
    line-height: 2em;
    color: #c4c4c4;
  }

  .go {
    position: relative;
    height: 2em;

    i {
      color: gray;
      font-size: 18px;
      position: absolute;
      right: 10px;
      bottom: 10px;
      transform: rotate(-90deg);
      transition: right $selectDuration ease-out;
    }
  }

  &:hover {
    transform: translate(0, -10px);
    cursor: pointer;
    box-shadow: 15px 20px 18px -12px #DDD, -10px 20px 18px -12px #DDD;

    i {
      right: 0;
      color: #005bb5;
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
</style>
