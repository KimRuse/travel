<template>
  <div>
    <Banner />
    <Header />
    <div class="content"></div>
  </div>
</template>

<script>
import Banner from './detail/components/Banner'
import Header from './detail/components/Header'

export default {
  name: 'Detail',
  components: {
    Banner, Header
  }
}
</script>

<style lang="scss" scoped>
.content {
  height: 50rem;
}
</style>
