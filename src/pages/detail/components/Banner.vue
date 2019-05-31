<template>
  <div>
    <div class="banner" @click="handleShowGallary">
      <img class="banner-img" :src="bannerImg" />
      <div class="banner-info">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-number">
          <span class="fa fa-picture-o"></span>
          {{bannerImg.length}}
        </div>
      </div>
    </div>
    <Gallary :imgs="gallaryImgs" v-if="showGallary" @change="changeShow" />
  </div>
</template>

<script>
import Gallary from '@/pages/common/gallary/Gallary.vue'

export default {
  name: 'Banner',
  components: {
    Gallary
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data() {
    return {
      showGallary: false,
    }
  },
  methods: {
    handleShowGallary () {
      this.showGallary = true
    },
    changeShow () {
      this.showGallary =false
    }
  }
}
</script>

<style lang="scss" scoped>
.banner {
  position: relative;
  font-size: .32rem;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;
  color: #fff;
  .banner-img {
    width: 100%;
  }
  .banner-info {
    display: flex;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    line-height: .6rem;
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));
    .banner-title {
      flex: 1;
      padding: 0 .2rem;
    }
    .banner-number {
      font-size: .24rem;
      padding: 0 .4rem;
      height: .32rem;
      line-height: .32rem;
      margin: .14rem .15rem;
      border-radius: .2rem;
      background-color: rgba(0, 0, 0, .8);
    }
  }
}
</style>
