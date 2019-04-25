<template>
  <swiper :options="swiperOptions">
    <swiper-slide>
      <img src="http://www.chinaant.net:6061/File/getFile/IndexBannerImg/1111115700992212992">
    </swiper-slide>
    <swiper-slide>
      <img src="http://www.chinaant.net:6061/File/getFile/IndexBannerImg/1100671771759083520">
    </swiper-slide>
    <swiper-slide>
      <img src="http://www.chinaant.net:6061/File/getFile/IndexBannerImg/1112623848437579776">
    </swiper-slide>
  </swiper>
</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: "Banner",
  components: {
    swiper,
    swiperSlide
  },
  data() {
    return {
      swiperOptions: {
        autoplay: true,
        delay: 5000,
        loop: true,
        disableOnInteraction: false
      }
    }
  }
}
</script>

<style scoped lang="postcss">
img {
  width: 100%;
  &:hover {
    cursor: pointer;
  }
}
</style>