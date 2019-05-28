<template>
  <div class="warpper">
    <swiper :options="swiperOption">
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {id: '0001',imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/60904fc24f223e0db5aee3c6148e641f.jpg_750x200_b1b90a19.jpg'},
        {id: '0002',imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/e1e587f554e5a8372be44a4c6b73a5cf.jpg_750x200_5732f03f.jpg'},
        {id: '0003',imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/505d7ffbfedeeeb5fb45e118adf4c7d0.jpg_750x200_2fe3d2e3.jpg'}
      ]
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
