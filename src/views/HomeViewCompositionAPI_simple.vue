<template>
 <div class="home">
  <h2>{{ appTitle }}</h2>
  <h3>{{ counterData.title }}:</h3>
  <div>
    <button @click="excecute('minus')" class="btn">-</button>
    <span class="counter">{{ counterData.count }}</span>
    <button @click="excecute('plus')" class="btn">+</button>
  </div>

  <div class="edit">
    <h4>Edit coutner title:</h4>
    <input v-model="counterData.title" type="text" name="" id="">
  </div>
 </div>
</template>

<script setup>
  // script setup: take off some boilerplate code like export default and return
  import { ref,reactive } from 'vue'

  const appTitle = 'My Vue 3 App' //non-reactive data

  // const counter = ref(0); //ref data
  // const coutnerTitle = ref('my counter')

  const counterData = reactive({ //reactive data
    count: 0,
    title: 'my counter'
  })

  const excecute = (operator = null) => {
    if(operator === 'plus') {
      // counter.value++
      counterData.count++
    }
    if(operator === 'minus') {
      // counter.value--
      counterData.count--
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

  .edit {
    margin-top: 20px;
  }
</style>