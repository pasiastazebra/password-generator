<template>
  <div class="window">
    <h1 class="window-title">PASSWORD GENERATOR</h1>
    <div class="window-section">
      <h2 class="window-section-title">Length</h2>
      <input type="number" class="window-section-input" placeholder="Length" v-model="length">
      <p> {{ length }} </p>
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Ammount of numbers</h2>
      <input type="number" class="window-section-input" placeholder="Ammount of numbers" v-model="amountOfNumbers">
      <p> {{ amountOfNumbers }} </p>
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Ammount of special characters</h2>
      <input type="number" class="window-section-input" placeholder="Ammount of special characters" v-model="amountOfSpecChar">
      <p> {{ amountOfSpecChar }} </p>
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Required phrase</h2>
      <input type="text" class="window-section-input" placeholder="Requeired phrase" v-model="phrase">
      <p> {{ phrase }} </p>
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Result</h2>
      <input type="text" class="window-section-input" placeholder="Result" :value="result" readonly>
      <p> {{ result }} </p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'WindowContent',

  data() {
    return {
      length: '',
      amountOfNumbers: '',
      amountOfSpecChar: '',
      phrase: '',
      result: 'test'
    };
  }
};
</script>

<style scoped lang="scss">

</style>
