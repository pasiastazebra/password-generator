<template>
  <WindowContent></WindowContent>
  <SiteFooter></SiteFooter>
</template>

<script>
import WindowContent from './components/WindowContent.vue';
import SiteFooter from './components/SiteFooter.vue';

export default {
  name: 'App',
  components: {
    WindowContent,
    SiteFooter
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  margin-top: 60px;
  margin-bottom: 0%;
}
.bottomWaves {
  position:absolute;
  bottom:0;
}
</style>
