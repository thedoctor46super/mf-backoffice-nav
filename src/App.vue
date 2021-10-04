<template>
  <div id="app">
    <SideNav />
  </div>
</template>

<script>
import SideNav from './components/SideNav.vue';

export default {
  name: 'App',
  components: {
    SideNav,
  },
};
</script>

<style scoped lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
