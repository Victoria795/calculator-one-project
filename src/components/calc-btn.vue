<template>
  <button 
  class="calc__btn"
  :class="className"
  type="button"
  >{{symbol}}</button>
</template>
<script>
//import { computed } from '@vue/reactivity';
export default {
  name: 'calc-btn',
  props: {
    symbol: String,
    equal: {
      type: Boolean,
      default: false
    },
    sign: {
      type: Boolean,
      default: false
    },
    delete: {
      type: Boolean,
      default: false
    },
  },
  data() {
      
  },
  computed: {
     className() {
      return {
        "calc__btn_equal": this.equal,
        "calc__btn_sign": this.sign,
        "calc__btn_delete": this.delete
      }
     }
  },
  methods: {
      
  }
}
</script>

<style>
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
