<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-t">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.$store.state.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-t">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper"
               v-for="item of hot"
               :key="item.id"
               @click="handleChangeCity(item.name)"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area"
           v-for="(item, name, index) of cities" :key="index"
           :ref="name"
      >
        <div class="title border-t">{{name}}</div>
        <div class="item-list">
          <div class="item border-t"
               v-for="innerItem of item"
               :key="innerItem.id"
               @click="handleChangeCity(innerItem.name)"
          >{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'

export default {
  name: "List",
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  methods: {
    handleChangeCity (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
};
</script>

<style lang="scss" scoped>
.border-t {
  border-bottom: 0.02rem solid #ccc;
}
.list {
  overflow: hidden;
  position: absolute;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  .title {
    height: 0.54rem;
    line-height: 0.54rem;
    background-color: #eee;
    padding-left: 0.2rem;
    color: #666;
    font-size: 0.32rem;
  }
  .button-list {
    font-size: 0.32rem;
    overflow: hidden;
    padding: 0.1rem 0.6rem 0.1rem 0.1rem;
    .button-wrapper {
      float: left;
      width: 33.33%;
      .button {
        margin: 0.1rem;
        text-align: center;
        border: 0.02rem solid #ccc;
        border-radius: 0.06rem;
      }
    }
  }
  .item-list {
    .item {
      font-size: .32rem;
      line-height: .76rem;
      padding-left: .2rem;
    }
  } 
}

</style>
