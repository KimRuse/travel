<template>
  <div class="header">
    城市选择
    <router-link to="/">
    <span class="fa fa-angle-left"></span>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss" scoped>
@import '@/assets/common/varibles.scss';
.header {
  position: relative;
  overflow: hidden;
  height: .86rem;
  line-height: .86rem;
  text-align: center;
  color: #fff;
  background-color: $bgColor;
  font-size: .32rem;
  .fa-angle-left {
    position: absolute;
    left: .3rem;
    top: .1rem;
    font-size: .64rem;
    color: #fff;
  }
}
</style>
