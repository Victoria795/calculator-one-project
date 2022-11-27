<template>
<div class="wrapper">
  <div class="container">
  <div class="calc-description">{{currentResult || 0}}</div>
  <div class="calc-result"><hr>{{finalResult || 0}}</div>
  <calc-btn :delete="true" symbol="C" @:click = "clean()"/>
  <calc-btn :sign="true" symbol="%" @:click = "percentage()"/>
  <calc-btn :sign="true" symbol="&#8656;" @:click = "erase()"/>
  <calc-btn :sign="true" symbol="&#247;" @:click = "input('/')"/>

  <calc-btn symbol="7" @:click = "input(7)"/>
  <calc-btn symbol="8" @:click = "input(8)"/>
  <calc-btn symbol="9" @:click = "input(9)"/>
  <calc-btn :sign="true" symbol="*" @:click = "input('*')"/>

  <calc-btn symbol="4"  @:click = "input(4)"/>
  <calc-btn symbol="5" @:click = "input(5)"/>
  <calc-btn symbol="6" @:click = "input(6)"/>
  <calc-btn :sign="true" symbol="-" @:click = "input('-')"/>

  <calc-btn symbol="1" @:click = "input(1)"/>
  <calc-btn symbol="2" @:click = "input(2)"/>
  <calc-btn symbol="3" @:click = "input(3)"/>
  <calc-btn :sign="true" symbol="+" @:click = "input('+')"/>

  <calc-btn :sign="true" symbol="." @:click = "dot()"/>
  <calc-btn symbol="0" @:click = "input(0)"/>
  <calc-btn :equal="true" symbol="=" @:click = "count()"/>
  </div>
</div>
</template> 
<script>

import calcBtn from './components/calc-btn.vue'

export default {
  name: 'App',
  components: {
    calcBtn
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
    dot(){ if(this.currentResult.length === 0 || this.currentResult.endsWith('+') 
    || this.currentResult.endsWith('-') || this.currentResult.endsWith('*') || this.currentResult.endsWith('/')){
      this.input('0.');
    }
    else{
      this.input('.');
    }
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
