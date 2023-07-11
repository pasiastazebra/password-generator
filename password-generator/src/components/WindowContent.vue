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
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Required phrase</h2>
      <input type="text" class="window-section-input" placeholder="Requeired phrase" v-model="phrase">
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Result</h2>
      <input type="text" class="window-section-input" placeholder="Result" :value="result" readonly>
    </div>
  </div>
</template>

<script>
//2D arrays for generating the password

const letters = [['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J'],
                 ['K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T'], 
                 ['U', 'V', 'W', 'X', 'Y', 'Z', 'A', 'B', 'C', 'D']];

const specChar = [['!', '@', '#', '$', '%', '^', '&', '*', '(', ')'], 
                  ['[', ']', '{', '}', '?', '<', '>', ',', '.', '+'], 
                  ['-', '=', '/', '|', '\\', '_', "'", '`', '"', '~']];

//function for randomizing 

const randomArray = () => {
  return [Math.floor(Math.random() * 3), Math.floor(Math.random() * 9)];
}

export default {
  name: 'WindowContent',

  data() {
    return {
      
      length: '',
      amountOfNumbers: '',
      amountOfSpecChar: '',
      phrase: '',
      result: 'test',

    };
  }
};
</script>

<style scoped lang="scss">

</style>
