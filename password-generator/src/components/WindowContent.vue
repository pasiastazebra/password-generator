<template>
  <div class="window">
    <h1 class="window-title">PASSWORD GENERATOR</h1>
    <div class="window-section">
      <h2 class="window-section-title">Length</h2>
      <input type="number" class="window-section-input" placeholder="Length" v-model="length">
      <p>{{ length }}</p>
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Ammount of numbers</h2>
      <input type="number" class="window-section-input" placeholder="Ammount of numbers" v-model="amountOfNumbers">
      <p>{{ amountOfNumbers }}</p>
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Ammount of special characters</h2>
      <input type="number" class="window-section-input" placeholder="Ammount of special characters" v-model="amountOfSpecChar">
    </div>
    <div class="window-section">
      <h2 class="window-section-title" @mouseenter="generatePassword">Result</h2>
      <input type="text" class="window-section-input" placeholder="Result" :value="result" readonly>
    </div>
  </div>
</template>

<script>
const letters = [['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J'],
                 ['K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T'],
                 ['U', 'V', 'W', 'X', 'Y', 'Z', 'A', 'B', 'C', 'D']];

const specChar = [['!', '@', '#', '$', '%', '^', '&', '*', '(', ')'],
                  ['[', ']', '{', '}', '?', '<', '>', ',', '.', '+'],
                  ['-', '=', '/', '|', '\\', '_', "'", '`', '"', '~']];

export default {
  name: 'WindowContent',
  data() {
    return {
      length: '',
      amountOfNumbers: '',
      amountOfSpecChar: '',
      result: '',
      limitOfNumbers: 0,
      limitOfCharacters: 0,
    };
  },
  methods: {
    randomArray() {
      return [Math.floor(Math.random() * 3), Math.floor(Math.random() * 9)];
    },

    //it would be nice to separate it into more function for code clarity
    charPicker() {
      const [rowIndex, columnIndex] = this.randomArray();
      if (this.limitOfNumbers === 0) {
        if (this.limitOfCharacters === 0) {
          return letters[rowIndex][columnIndex];
          //random to uper or lower case - to do - it can be separated function
        } else {
          this.limitOfCharacters--;
          return specChar[rowIndex][columnIndex];
        }
      } else if (this.limitOfCharacters === 0) {
        this.limitOfNumbers--;
        return Math.floor(Math.random() * 9);
      } else {
        return letters[rowIndex][columnIndex];
        //random to uper or lower case - to do - it can be separated function
      }
    },

    //final password generating function have to be there
    passwordGenerator() {
      //limiters
      this.limitOfNumbers = parseInt(this.amountOfNumbers);
      this.limitOfCharacters = parseInt(this.amountOfSpecChar);
      const allSymbols = parseInt(this.length);

      if (allSymbols !== this.limitOfCharacters + this.limitOfNumbers) {
        this.result = 'too much symbols';
      } else {
        this.result = '';
        for (let i = 0; i < allSymbols; i++) {
          this.result += this.charPicker();
        }
      }
    },
    generatePassword() {
      this.passwordGenerator();
    },
  },
};
</script>

<style scoped lang="scss">
/* Twój styl CSS */
</style>
