<template>
  <ul class="slide-list">
    <li class="item"
        v-for="(item, name) of cities"
        :key="name"
    >
    {{name}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'Alphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/common/varibles.scss';

.slide-list {
  font-size: .32rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: absolute;
  top: 1.58rem;
  right: 0;
  bottom: 0;
  width: .4rem;
  .item {
    text-align: center;
    line-height: .4rem;
    color: $bgColor;
  }
}
</style>
