<template>
  <div id="app">
    <keep-alive exclude="Detail">
      <router-view />
    </keep-alive>
  </div>
</template>

<script>
</script>

<style lang="css">
@import './assets/common/reset.css';
@import './assets/common/font-awesome.css';
@import './assets/common/border.css';

html {
  font-size: 50px;
}
</style>
