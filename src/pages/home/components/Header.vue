<template>
  <div class="header">
    <div class="header-left"><span class="fa fa-angle-left"></span></div>
    <div class="header-mid"><span class="fa fa-search"></span></div>
    <div class="header-right">{{this.city}}<span class="fa fa-caret-down"></span></div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    city: String
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/common/varibles.scss';
  .header {
    font-size: .32rem;
    display: flex;
    line-height: .86rem;
    background-color: $bgColor;
    color: #fff;
    .header-left {
      float: left;
      width: .64rem;
      .fa-angle-left {
        font-size: .64rem;
        position: relative;
        left: 10px;
        top: 5px;
      }
    }
    .header-mid {
      flex: 1;
      font-size: .46rem;
      color: #ccc;
      margin-top: 0.12rem;
      margin-left: 0.2rem;
      height: .64rem;
      line-height: .64rem;
      background-color: #fff;
      border-radius: 0.1rem;
      .fa-search {
        font-size: .32rem;
        position: relative;
        left: 8px;
        top: -2px;
      }
    }
    .header-right {
      float: right;
      width: 1.24rem;
      text-align: center;
      .fa-caret-down {
        position: relative;
        left: .04rem;
      }
    }
  }
</style>
