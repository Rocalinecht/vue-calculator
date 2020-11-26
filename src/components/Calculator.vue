<template>
  <div class="calculator">
    <div class="display">{{  current || '0'}}</div>
    <div @click="clear" class="btn">AC</div>
    <div @click="sign" class="btn">+/-</div>
    <div  @click="percent" class="btn">%</div>
    <div  @click="divide" class="btn operator">÷</div>

    <div @click="append('7')" class="btn">7</div>
    <div @click="append('8')" class="btn">8</div>
    <div @click="append('9')" class="btn">9</div>
    <div @click="times" class="btn operator">X</div>

    <div @click="append('4')" class="btn">4</div>
    <div @click="append('5')" class="btn">5</div>
    <div @click="append('6')" class="btn">6</div>
    <div @click="minus" class="btn operator">-</div>

    <div @click="append('1')" class="btn">1</div>
    <div @click="append('2')" class="btn">2</div>
    <div @click="append('3')" class="btn">3</div>
    <div @click="add" class="btn operator">+</div>

    <div @click="append('0')" class="btn zero">0</div>
    <div @click="dot" class="btn">,</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      current:'',
      operator: null,
    }
  },
  methods:{
    clear(){
      this.current='';
    },
    sign(){
      this.current = this.current.charAt(0) === '-' ?
        this.current.slice(1) : `-${this.current}`;
    },
    percent(){
      this.current = `${parseFloat(this.current) / 100 }`
    },
    append(number){
      this.current =  `${this.current} ${number}`;
    },
    dot(){
      if(this.current.indexOf('.') === -1){
          this.append('.')
      }
    },
    divide(){
      this.operator = (a, b) => a / b;
    },
    times(){
      this.operator = (a, b) => a * b;
    },
    minus(){
      this.operator = (a, b) => a - b;
    },
    add(){
      this.operator = (a, b) => a + b;
    }, 
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

.calculator{
  width: 400px;
  margin: 0 auto;
  font-size: 40px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-columns: minmax(50px, auto);
  font-family: 'Poppins', sans-serif;
}
.display{
  grid-column: 1 /5;
  background-color: #1C1C1C;
  color: #D4D4D2;
  /* text-align: end;
  padding-right: 10%; */
}
.zero{
  grid-column: 1 / 3;
}
.btn{
  background-color: #D4D4D2;
  border: 1px solid #1C1C1C;
}
.operator{
  background-color: #FF9500;
  color: white;
}
</style>
