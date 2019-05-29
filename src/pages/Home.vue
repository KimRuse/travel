<template>
  <div>
    <Header :city="city" />
    <Swiper :swiperList="swiperList" />
    <Icons :iconList="iconList" />
    <Recommend :recommendList="recommendList" />
    <Weekend :weekendList="weekendList" />
  </div>
</template>

<script>
import Header from './home/components/Header'
import Swiper from './home/components/Swiper'
import Icons from './home/components/Icons'
import Recommend from './home/components/Recommend'
import Weekend from './home/components/Weekend'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    Header,
    Swiper,
    Icons,
    Recommend,
    Weekend
  },
  data () {
    return {
      city: '武汉',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res) {
        this.swiperList = res.swiperList
        this.iconList = res.iconList
        this.recommendList = res.recommendList
        this.weekendList =res.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>
</style>
