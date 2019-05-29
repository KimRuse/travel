<template>
  <div>
    <Header />
    <Search />
    <List :cities="cities"
          :hot="hotCities"
          :letter="letter"
     />
    <Alphabet 
      :cities="cities"
      @change="handleLetterChange"
     />
  </div> 
</template>

<script>
import Header from './city/components/Header'
import Search from './city/components/Search'
import List from './city/components/List'
import Alphabet from './city/components/Alphabet'
import axios from 'axios';

export default {
  name: 'City',
  components: {
    Header, Search, List, Alphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/city.json')
        .then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handleLetterChange (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style>

</style>
