<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="输入城市名或拼音" />
  </div>
</template>

<script>
export default {
  name: 'Search'
}
</script>

<style lang="scss" scoped>
@import '@/assets/common/varibles.scss';
.search {
  height: .72rem;
  padding: 0 .1rem;
  background-color: $bgColor;
  .search-input {
    box-sizing: border-box;
    padding: 0 .1rem;
    width: 100%;
    height: .62rem;
    line-height: .62rem;
    text-align: center;
    border-radius: .06rem;
    transform: translateY(-.375rem);
    color: #666; 
  }
}
</style>