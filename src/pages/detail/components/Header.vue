<template>
  <div>
    <router-link 
      tag="div"
      class="header-abs"
      to="/"
      v-show="showAbs"
    >
      <span class="fa fa-angle-left"></span>
    </router-link>
    <div
      class="header-fixed"
      v-show="!showAbs"
      :style="opacity"
    >
      景点详情
      <router-link to="/">
      <span class="fa fa-angle-left"></span>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      showAbs: true,
      opacity: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if ( top > 60 ) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacity = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="scss" scoped>
@import '@/assets/common/varibles.scss';
.header-abs {
  position: absolute;
  left: .2rem;
  top: .2rem;
  width: .8rem;
  height: .8rem;
  border-radius: .4rem;
  background-color: rgba(0, 0, 0, .8);
  .fa-angle-left {
    position: absolute;
    left: .22rem;
    top: 0;
    font-size: .8rem;
    color: #fff;
  }
}
.header-fixed {
  z-index: 2;
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
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

