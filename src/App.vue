<template>
<div class="wrapper">
  <div class="container">
  <div class="calc-description">{{currentResult || 0}}</div>
  <div class="calc-result"><hr>{{finalResult || 0}}</div>
  <AppBtn :delete="true" @click = "clean()">C</AppBtn>
  <AppBtn :sign="true" @click = "percentage()">%</AppBtn>
  <AppBtn :sign="true" @click = "erase()">&#8656;</AppBtn>
  <AppBtn :sign="true" @click = "input('/')">&#247;</AppBtn>

  <AppBtn @click = "input(7)">7</AppBtn>
  <AppBtn @click = "input(8)">8</AppBtn>
  <AppBtn @click = "input(9)">9</AppBtn>
  <AppBtn :sign="true" @click = "input('*')">*</AppBtn>

  <AppBtn @click = "input(4)">4</AppBtn>
  <AppBtn @click = "input(5)">5</AppBtn>
  <AppBtn @click = "input(6)">6</AppBtn>
  <AppBtn :sign="true" @click = "input('-')">-</AppBtn>

  <AppBtn symbol="1" @click = "input(1)">1</AppBtn>
  <AppBtn symbol="2" @click = "input(2)">2</AppBtn>
  <AppBtn symbol="3" @click = "input(3)">3</AppBtn>
  <AppBtn :sign="true" @click = "input('+')">+</AppBtn>

  <AppBtn :sign="true" @click = "dot()">.</AppBtn>
  <AppBtn @click = "input(0)">0</AppBtn>
  <AppBtn :equal="true" @click = "count()">=</AppBtn>
  </div>
</div>
</template> 
<script>

import AppBtn from './components/AppBtn.vue'


export default {
  name: 'App',
  components: {
    AppBtn
  },
  data() {
    return{
    currentResult : '',
    finalResult: '',
    }
  },
  methods: {
    input(symbol) {
      this.currentResult += symbol;
    },
    clean() {
      this.currentResult = '';
      this.finalResult = '';
    },
    erase(){
      this.currentResult = this.currentResult.slice(0, -1);
    },
    dot() {
    if (!Number.isInteger(+this.currentResult[this.currentResult.length - 1])) {
    return this.input('0.');
    }  
    this.input('.');
    },
    percentage(){
      this.currentResult = this.currentResult/100;
    },
    count(){
      this.finalResult = eval(this.currentResult);
    },
}
}
</script>

<style>
@import 'assets/index.css';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: white;
}
.wrapper{
  position: absolute;
  width: 100%;
  height: 100%;
  background: #ced0da;
  overflow: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}
.container{
  height: 550px;
  width: 400px;
  background-color: rgb(114, 143, 138);
  padding: 10px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}
hr {
  border: none;
  background-color: white;
  height: 0.1px;
  opacity: 0.5;
  width: 100%;
}
.calc-description{
  grid-column: 1 / -1;
  font: normal 400 16px/16px 'Avenir', sans-serif;
  display: flex;
  align-items: flex-end;
  justify-content: flex-end;
}
.calc-result{
  padding-bottom: 15px;
  grid-column: 1 / -1;
  font: normal 700 38px/16px 'Avenir', sans-serif;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
</style>
