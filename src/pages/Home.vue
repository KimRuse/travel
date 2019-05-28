<template>
  <div>
    <Header />
    <Swiper />
    <Icons />
    <Recommend />
    <Weekend />
  </div>
</template>

<script>
import Header from './home/components/Header'
import Swiper from './home/components/Swiper'
import Icons from './home/components/Icons'
import Recommend from './home/components/Recommend'
import Weekend from './home/components/Weekend'

export default {
  name: 'Home',
  components: {
    Header,
    Swiper,
    Icons,
    Recommend,
    Weekend
  }
}
</script>

<style>

</style>
