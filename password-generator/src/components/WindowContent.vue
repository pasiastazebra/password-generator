<template>
    <div class="window">
        <h1 class="window-title">title placeholder</h1>
        <WindowSection/>
    </div>
</template>
  
  <script>
  import WindowSection from './WindowComponents/WindowSection.vue';

  export default {
    name: 'WindowContent',
    components: {
        WindowSection,
    },
    props: {
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
 
  </style>
  