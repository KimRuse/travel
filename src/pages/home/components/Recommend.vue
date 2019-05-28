<template>
  <div>
    <div class="recommend-title">热销推荐</div> 
    <ul>
      <li class="item"
          v-for="item of recommendList"
          :key="item.id"
      >
          <img :src="item.recUrl" class="item-img" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <div class="item-star">
            <strong class="fa star" :style="{width: item.level}">&#xf005&#xf005&#xf005&#xf005&#xf005</strong>
            <span class="fa star-o">&#xf006&#xf006&#xf006&#xf006&#xf006</span>
            <p class="item-discuss">{{item.discuss}} 评论</p>  
          </div>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Recommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        recUrl: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
        title: '上海迪士尼乐园',
        level: '50%',
        discuss: 21345
      },{
        id: '0002',
        recUrl: 'http://img1.qunarzz.com/sight/p0/1904/d5/d579b03a110d75a8a3.img.jpg_200x200_740bd4c0.jpg',
        title: '上海野生动物园',
        level: '70%',
        discuss: 9132
      },{
        id: '0003',
        recUrl: 'http://img1.qunarzz.com/sight/p0/1811/e4/e4b9b471d2afc473a3.img.jpg_200x200_9a7794fc.jpg',
        title: '上海欢乐谷',
        level: '90%',
        discuss: 3214
      },{
        id: '0004',
        recUrl: 'http://img1.qunarzz.com/tuan/team2/1507/2c/83e0e0e7ae082a.jpg_200x200_6d7378b2.jpg',
        title: '上海东方明珠',
        level: '10%',
        discuss: 43345
      }]
    }
  }
}
</script>

<style lang="scss" scoped>
.recommend-title {
  font-size: .32rem;
  margin-top: .2rem;
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
