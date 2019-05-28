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
  data () {
    return {
      weekendList: [{
        id: '0001',
        weekUrl: 'http://img1.qunarzz.com/sight/source/1505/7d/df6ff468331c43.jpg_r_640x214_1f3783d0.jpg',
        title: '上海必打卡',
        desc: '中西合璧，初代和传统各有各的博彩'
      },{
        id: '0002',
        weekUrl: 'http://img1.qunarzz.com/sight/source/1603/ad/69b0fc5f48ad5f.jpg_r_640x214_b0fd5c7b.jpg',
        title: '周末亲子爱玩',
        desc: '走进自然或玩转乐园，感知大千世界，游乐项目惊险刺激，特色表演异彩纷呈，等你们~'
      },{
        id: '0003',
        weekUrl: 'http://img1.qunarzz.com/sight/source/1511/1d/fe098e8cfec117.jpg_r_640x214_a9be292a.jpg',
        title: '上海城市观光',
        desc: '中西合璧，初代和传统各有各的博彩来这里寻找你所不认识的魔都 ，感受云端漫步，品味老上海风情，享受休闲时光'
      },]  
    }
    
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/common/mixins.scss';

.recommend-title {
  font-size: .32rem;
  margin-top: .2rem;
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
