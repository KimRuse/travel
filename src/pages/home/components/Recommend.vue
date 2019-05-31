<template>
  <div>
    <div class="recommend-title">热销推荐</div> 
    <ul>
      <router-link
          tag="li"
          class="item"
          v-for="item of recommendList"
          :key="item.id"
          :to="'/detail/'+item.id"
      >
          <img :src="item.recUrl" class="item-img" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <div class="item-star">
            <strong class="fa star" :style="{width: item.level}">&#xf005;&#xf005;&#xf005;&#xf005;&#xf005;</strong>
            <span class="fa star-o">&#xf006;&#xf006;&#xf006;&#xf006;&#xf006;</span>
            <p class="item-discuss">{{item.discuss}} 评论</p>  
          </div>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Recommend',
  props: {
    recommendList: Array
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="scss" scoped>
.recommend-title {
  font-size: .32rem;
  margin-top: .1rem;
  line-height: .8rem;
  background-color: #eee;
  text-indent: .2rem;
}
.item {
  overflow: hidden;
  display: flex;
  height: 1.9rem;
  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: .1rem;
  }
  .item-info {
    flex: 1;
    padding: .1rem;
    .item-title {
      line-height: .54rem;
      font-size: .32rem;
    }
    .item-star {
      position: relative;
      height: .6rem;
      width: 1.486rem;
      .star, .star-o {
        overflow: hidden;
        position: absolute;
        left: .1rem;
        top: .1rem;
        font-size: .32rem;
        color: #ff9300;
      }
      .item-discuss {
        position: absolute;
        left: 1.8rem;
        top: .12rem;
        font-size: .3rem;
        width: 1.6rem;
      }   
    }
    .item-button {
      line-height: .44rem;
      background-color: #ff9300;
      padding: 0 .2rem;
      border-radius: .06rem;
      transform: translateY(-.45rem);
    }
  }
}
</style>
