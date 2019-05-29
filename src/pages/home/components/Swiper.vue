<template>
  <div class="warpper">
    <swiper :options="swiperOption" >
      <swiper-slide v-for="item of swiperList" :key="item.id"><img class="swiper-img" :src="item.imgUrl" /></swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>  
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: "Swiper",
  components: {
    swiper,
    swiperSlide
  },
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000,
        autoplayDisableOnInteraction: false
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.warpper >>> .swiper-pagination-bullet-active {
  background: #fff;
}
.warpper {
  //防抖动
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 26.66%;
  .swiper-img {
    width: 100%;
  }
}
</style>
