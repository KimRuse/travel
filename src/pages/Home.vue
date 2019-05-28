<template>
  <div>
    <Header />
    <Swiper />
    <Icons />
  </div>
</template>

<script>
import Header from './home/components/Header'
import Swiper from './home/components/Swiper'
import Icons from './home/components/Icons'

export default {
  name: 'Home',
  components: {
    Header,
    Swiper,
    Icons
  }
}
</script>

<style>

</style>
