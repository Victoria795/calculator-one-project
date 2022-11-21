<template>
<div class="wrapper">
  <div class="container">
  <div class="calc-description">120-50+100</div>
  <div class="calc-result"><hr>170</div>
  <button class="calc__btn calc__btn_delete" type="button">C</button>
  <button class="calc__btn calc__btn_sign" type="button">%</button>
  <button class="calc__btn calc__btn_sign" type="button">&#8656;</button>
  <button class="calc__btn calc__btn_sign" type="button">&#247;</button>

  <button class="calc__btn" type="button">7</button>
  <button class="calc__btn" type="button">8</button>
  <button class="calc__btn" type="button">9</button>
  <button class="calc__btn calc__btn_sign" type="button">&#215;</button>

  <button class="calc__btn" type="button">4</button>
  <button class="calc__btn" type="button">5</button>
  <button class="calc__btn" type="button">6</button>
  <button class="calc__btn calc__btn_sign" type="button">-</button>  

  <button class="calc__btn" type="button">1</button>
  <button class="calc__btn" type="button">2</button>
  <button class="calc__btn" type="button">3</button>    
  <button class="calc__btn calc__btn_sign" type="button">+</button>

  <button class="calc__btn calc__btn_sign" type="button">.</button>
  <button class="calc__btn" type="button">0</button>
  <button class="calc__btn calc__btn_equal" type="button">=</button>
  </div>
</div>
</template> 
<script>
/*import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}*/
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
.calc__btn{
  font: normal 700 26px/16px 'Avenir', sans-serif;
  background: #030d11;
  border: none;
  box-shadow: 0px 3px 3px rgb(196, 193, 193);
  color: white;
}
.calc__btn_equal{
  grid-column: 3 / -1;
  background: rgb(191, 248, 250);
  color: #030d11;
}
.calc__btn_sign{
  background: #134c54;
}
.calc__btn_delete{
  background:rgb(191, 248, 250);
  color: #030d11;
}
</style>
