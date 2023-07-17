<template>
  <div class="window">
    <div class="window-header">
      <h1 class="window-header-title">Password Generator</h1>
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Length</h2>
      <input type="number" class="window-section-input" placeholder="Length" v-model="length">
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Ammount of numbers</h2>
      <input type="number" class="window-section-input" placeholder="Amm. of numbers" v-model="amountOfNumbers">
    </div>
    <div class="window-section">
      <h2 class="window-section-title">Ammount of special characters</h2>
      <input type="number" class="window-section-input" placeholder="Amm. of special characters" v-model="amountOfSpecChar">
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

    returnNumber() {
      this.limitOfNumbers--;
      return Math.floor(Math.random() * 10);
    },
    
    returnChar(insideRowIndex, insideColumnIndex) {
      this.limitOfCharacters--;
      return specChar[insideRowIndex][insideColumnIndex];
    },

    returnLetter(insideRowIndex, insideColumnIndex) {
      if (Math.floor(Math.random() * 2) === 1) {
        return letters[insideRowIndex][insideColumnIndex].toUpperCase();
      } else {
        return letters[insideRowIndex][insideColumnIndex].toLowerCase();
      }
    },

    //it would be nice to separate it into more function for code clarity
    charPicker() {
      const [rowIndex, columnIndex] = this.randomArray();
      if (this.limitOfNumbers === 0) {
        if (this.limitOfCharacters === 0) {
         return this.returnLetter(rowIndex, columnIndex);
        } else {
         return this.returnChar(rowIndex, columnIndex);
        }
      } else if (this.limitOfCharacters === 0) {
        return this.returnNumber();
      } else {
        if (Math.floor(Math.random() * 2) === 1) {
         return this.returnNumber();
        } else {
         return this.returnChar(rowIndex, columnIndex);
        }
      }
    },

    //final password generating function have to be there
    passwordGenerator() {
      //limiters
      this.limitOfNumbers = parseInt(this.amountOfNumbers);
      this.limitOfCharacters = parseInt(this.amountOfSpecChar);
      const allSymbols = parseInt(this.length);

      if (allSymbols < this.limitOfCharacters + this.limitOfNumbers) {
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
  //variables
  $primaryColor: #e9e9e9;
  $secondaryColor: #515151;
  $greenColor: #159957;
  
 .window {
  //borders
  border-radius: 5px;
  box-shadow: 14px 14px 16px -11px $greenColor;

  background: $primaryColor;
  margin: 5% 30%;
  padding-bottom: 15px;
  max-width: 50%;

  &-header{
    background: $greenColor;
    border-radius: 5px 5px 0px 0px;

    &-title {
      color: $primaryColor;
      font-weight: 600;
      text-align: center;
    }
  }

  &-section {
    margin: 15px;

   &-title {
     color: $secondaryColor;
     font-weight: 400;
   }

  }
 }
</style>
