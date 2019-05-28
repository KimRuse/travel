<template>
  <div>
    <Header />
    <Swiper />
    <Icons />
    <Recommend />
  </div>
</template>

<script>
import Header from './home/components/Header'
import Swiper from './home/components/Swiper'
import Icons from './home/components/Icons'
import Recommend from './home/components/Recommend'

export default {
  name: 'Home',
  components: {
    Header,
    Swiper,
    Icons,
    Recommend
  }
}
</script>

<style>

</style>
