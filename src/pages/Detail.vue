<template>
  <div>
    <Banner
      :sightName="sightName"
      :bannerImg="bannerImg"
      :gallaryImgs="gallaryImgs"
    />
    <Header />
    <List :list="list" />
    <div class="content"></div>
  </div>
</template>

<script>
import Banner from './detail/components/Banner'
import Header from './detail/components/Header'
import List from './detail/components/List'
import axios from 'axios'

export default {
  name: 'Detail',
  components: {
    Banner, Header, List
  },
  data() {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleDataSucc)
    },
    handleDataSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.categoryList
      } 
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="scss" scoped>
.content {
  height: 50rem;
}
</style>
