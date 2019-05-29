<template>
  <div>
    <Header />
    <Search />
  </div>
  
</template>

<script>
import Header from './city/components/Header'
import Search from './city/components/Search'

export default {
  name: 'City',
  components: {
    Header, Search
  }
}
</script>

<style>

</style>
