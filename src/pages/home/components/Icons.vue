<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon"
             v-for="item of page"
             :key="item.id"
        >
          <div class="icon-img">
            <img class="icon-img-content" :src= 'item.iconUrl' />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  name: 'Icons',
  components: {
    swiper, swiperSlide
  },
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
          loop: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/common/varibles.scss';
@import '@/assets/common/mixins.scss';

.icons >>> .swiper-container {
  height: 0;
  padding-bottom: 50%;
}

.icons {
  width: 100%;
  overflow: hidden;
  height: 0;
  padding-bottom: 50%;
  margin-top: .1rem;
  .icon {
    position: relative;
    float: left;
    width: 25%;
    height: 0;
    padding-bottom: 25%;
    .icon-img {
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: .44rem;
      .icon-img-content {
        display: block;
        margin: 0 auto;
        height: 100%;
      }
    }
    .icon-desc {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      height: .44rem;
      line-height: .44rem;
      font-size: .32rem;
      color: $darkTextColor;
      text-align: center;
      @include ellipsis;
    }
  }
}
</style>
