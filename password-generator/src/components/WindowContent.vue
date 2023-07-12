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
      <h2 class="window-section-title" @mouseover="passwordGenerator">Result</h2>
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

let limitOfNumbers = 0;
let limitOfCharacters = 0;

//function for randomizing 

const randomArray = () => {
  return [Math.floor(Math.random() * 3), Math.floor(Math.random() * 9)];
}

//final password generating function have to be there
const passwordGenerator = () => {
  //limiters
  let limitOfNumbers = parseInt(this.amountOfNumbers);
  let limitOfCharacters = parseInt(this.amountOfSpecChar);
  const allSymbols = parseInt(this.length);

  if (allSymbols != limitOfCharacters + limitOfNumbers) {
    this.result = 'too much symbols' ;
  } else {
      for (let i = 0; i <= allSymbols; i++) {
        this.result[i] = this.charPicker();
      }
  }
  console.log(this.result);
}

//it would be nice to separate it into more function for code clarity
const charPicker = () => {
  let [rowIndex, columnIndex] = randomArray();
  if (limitOfNumbers === 0) {
    if (limitOfCharacters === 0){
      return letters[rowIndex][columnIndex];
      //random to uper or lower case - to do - it can be separated function
    }else {
      limitOfCharacters--;
      return specChar[rowIndex][columnIndex];
    }
  }
  else if (limitOfCharacters === 0){
    limitOfNumbers--;
    return Math.floor(Math.random() * 9);
  }else{
    return letters[rowIndex][columnIndex];
    //random to uper or lower case - to do - it can be separated function
  }
}


console.log(charPicker(1, 0));
console.log(charPicker(1, 1));
console.log(charPicker(0, 0));
console.log(charPicker(0, 1));

export default {
  name: 'WindowContent',

  data() {
    return {
      
      length: '',
      amountOfNumbers: '',
      amountOfSpecChar: '',
      result: 'test',

    };
  },
  methods: {
    charPicker,
    passwordGenerator,
    randomArray,
  }
};
</script>

<style scoped lang="scss">

</style>
