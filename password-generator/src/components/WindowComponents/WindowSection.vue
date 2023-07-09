<template>
    <div class="section">
        <p class="section-text">{{ text }}</p>
        <input type="text" class="section-input" v-model="value" :placeholder="inputPlaceholder">
        <br />
        You typed: <b>{{ value }}</b>
    </div>
</template>
  
  <script>
  export default {
    name: 'WindowSection',
    props: {
        text: String,
        inputPlaceholder: String
    },
    data() {
    return {
      value: '',
    };
  }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
 
  </style>
  