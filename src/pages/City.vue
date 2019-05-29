<template>
  <div>
    <Header />
    <Search />
    <List />
    <Alphabet />
  </div> 
</template>

<script>
import Header from './city/components/Header'
import Search from './city/components/Search'
import List from './city/components/List'
import Alphabet from './city/components/Alphabet'

export default {
  name: 'City',
  components: {
    Header, Search, List, Alphabet
  }
}
</script>

<style>

</style>
