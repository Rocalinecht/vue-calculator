<template>
  <div class="calculator">
    <div class="display">{{  current || '0'}}</div>
    <div @click="clear" class="btn">AC</div>
    <div @click="" class="btn">+/-</div>
    <div class="btn">%</div>
    <div class="btn operator">÷</div>

    <div class="btn">7</div>
    <div class="btn">8</div>
    <div class="btn">9</div>
    <div class="btn operator">X</div>

    <div class="btn">4</div>
    <div class="btn">5</div>
    <div class="btn">6</div>
    <div class="btn operator">-</div>

    <div class="btn">1</div>
    <div class="btn">2</div>
    <div class="btn">3</div>
    <div class="btn operator">+</div>

    <div class="btn zero">0</div>
    <div class="btn">,</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      current:'',
    }
  },
  methods:{
    clear(){
      this.current='';
    }
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
  text-align: end;
  padding-right: 10%;
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
