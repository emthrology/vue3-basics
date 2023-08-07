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
  export default {
    data() {
      return {
        counter: 0
      }
    },
    methods: {
      excecute(operator = null) {
        if(operator === 'plus') {
          this.counter++
        }
        if(operator === 'minus') {
          this.counter--
        }
      }
    },
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