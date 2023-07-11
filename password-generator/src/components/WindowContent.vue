<template>
  <div class="window">
    <h1 class="window-title">title placeholder</h1>
    <div class="window-section">
      <h2 class="window-section-title">Length</h2>
      <input type="number" class="window-section-input" placeholder="Length" :value="length">
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Ammount of numbers</h2>
      <input type="number" class="window-section-input" placeholder="Ammount of numbers" :value="ammountOfNumbers">
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Ammount of special characters</h2>
      <input type="number" class="window-section-input" placeholder="Ammount of special characters" :value="ammountOfSpecChar">
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Required phrase</h2>
      <input type="text" class="window-section-input" placeholder="Requeired phrase" :value="phrase">
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Result</h2>
      <input type="number" class="window-section-input" placeholder="Result" :value="result">
    </div>
  </div>
</template>

<script>

export default {
  name: 'WindowContent',
};
</script>

<style scoped lang="scss">

</style>
