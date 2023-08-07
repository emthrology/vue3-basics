<template>
 <div class="home">
  <div>
    <button @click="excecute('minus')" class="btn">-</button>
    <span class="counter">{{ counter }}</span>
    <button @click="excecute('plus')" class="btn">+</button>
  </div>
 </div>
</template>

<script>
  import { ref } from 'vue'
  export default {
   setup() {
      const counter = ref(0) //remember: ref is an object with a property called value
      const excecute = (operator = null) => {
        if(operator === 'plus') {
          counter.value++
        }
        if(operator === 'minus') {
          counter.value--
        }
      }
      return {
        counter,
        excecute
      }
   }
  }
</script>

<style>
  .home {
    text-align: center;
    padding: 20px;

  }
  .btn, .counter {
    font-size: 40px;
    margin: 10px; 
  }
</style>