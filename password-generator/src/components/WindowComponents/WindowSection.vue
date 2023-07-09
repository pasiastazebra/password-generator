<template>
    <div class="section">
        <p class="section-text">{{ text }}</p>
        <input type="text" class="section-input" :value="value" :placeholder="inputPlaceholder" @input="$emit('input', $event.target.value)">
        <br />
        You typed: <b>{{ value }}</b>
    </div>
</template>
  
  <script>
  export default {
    name: 'WindowSection',
    props: {
        text: String,
        inputPlaceholder: String,
        value: String
    },
  methods: {
   updateValue() {
     this.$emit('input', this.value);
   }
  }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
 
  </style>
  