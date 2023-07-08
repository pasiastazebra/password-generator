<template>
    <div class="section">
        <p class="section-text">{{ text }}</p>
        <input type="text" class="section-input" :value="inputPlaceholder">
    </div>
</template>
  
  <script>
  export default {
    name: 'WindowSection',
    props: {
        text: String,
        inputPlaceholder: String
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
 
  </style>
  