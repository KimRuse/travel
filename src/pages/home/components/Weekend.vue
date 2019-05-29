<template>
  <div>
    <div class="recommend-title">周末去哪儿</div> 
    <ul>
      <li class="item"
          v-for="item of weekendList"
          :key="item.id"
      >
        <div class="item-img-wrapper">
          <img :src="item.weekUrl" class="item-img" /> 
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Weekend',
  props: {
    weekendList: Array
  },
  data () {
    return { 
    }  
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/common/mixins.scss';

.recommend-title {
  font-size: .32rem;
  line-height: .8rem;
  background-color: #eee;
  text-indent: .2rem;
}
.item-img-wrapper {
  overflow: hidden;
  height: 0;
  padding-bottom: 33.4%;
  .item-img {
    width: 100%;
  }
}
.item-info {
  padding: .1rem;
  font-size: .32rem;
  .item-title {
    line-height: .54rem;
  }
  .item-desc {
    color: #ccc;
    @include ellipsis;
  }
}
</style>
