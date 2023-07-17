<template>
  <WindowContent></WindowContent>
</template>

<script>
import WindowContent from './components/WindowContent.vue';

export default {
  name: 'App',
  components: {
    WindowContent
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
.bottomWaves {
  position:absolute;
  bottom:0;
}
</style>
