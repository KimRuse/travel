<template>
  <div class="gallary"  @click="changeGallary">
    <div class="wrapper">
      <swiper :options="swiperOption" >
        <swiper-slide 
            v-for="(item, index) of imgs"
            :key="index"
        >
            <img class="gallary-img" :src="item" />
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  name: 'Gallary',
  components: {
    swiper, swiperSlide
  },
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    changeGallary () {
      this.$emit('change')
    }
  }
}
</script>

<style lang="scss" scoped>
.wrapper /deep/ .swiper-container {
  overflow: inherit;
}
.gallary {
  display: flex;
  flex-direction: column;
  justify-content: center;
  z-index: 99;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  background-color: #000;
  .wrapper {
    height: 0;
    width: 100%;
    padding-bottom: 100%;
    .gallary-img {
      width: 100%;
    }
    .swiper-pagination {
      font-size: .32rem;
      color: #fff;
      bottom: -1rem;
    }
  }
}
</style>
