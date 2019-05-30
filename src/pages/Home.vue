<template>
  <div>
    <Header />
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
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: [],
      lastCity: ''
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/index.json?city='+ this.$store.state.city)
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
    this.lastCity = this.$store.state.city
    this.getHomeInfo()
  },
  activated() {
    if (this.lastCity !== this.$store.state.city) {
      this.lastCity = this.$store.state.city
      this.getHomeInfo()
    }
  }
}
</script>

<style>
</style>
