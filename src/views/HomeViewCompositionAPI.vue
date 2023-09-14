<template>
 <div class="home">
  <h2 ref="appTitleRef">{{ appTitle }}</h2>
  <h3>{{ counterData.title }}:</h3>
  <div>
    <button @click="excecute('minus')" class="btn">-</button>
    <span class="counter">{{ counterData.count }}</span>
    <button @click="excecute('plus')" class="btn">+</button>
  </div>

  <p>This counter is {{ oddOrEven }} !!</p>

  <div class="edit">
    <h4>Edit coutner title:</h4>
    <input v-model="counterData.title" type="text" name="" id="">
  </div>
 </div>
</template>

<script setup>
  // by this way, keep the code consise by seperating it into different parts
  /*
    imports 
  */
  // script setup: take off some boilerplate code like export default and return
  import { ref,reactive, computed, watch, onMounted } from 'vue'


  /*
    app title
  */
  const appTitle = 'My Vue 3 App' //non-reactive data

  const appTitleRef = ref(null) 

  //mounted hook related to app title
  onMounted(() => {
    console.log('do stuff related to App title')
    console.log(`${appTitleRef.value.offsetWidth} px`)
  })

  /*
    counter
  */
  const counterData = reactive({ //reactive data
    count: 0,
    title: 'my counter'
  });

  // use getter to grep nested data
  watch(() => counterData.count, (newValue, oldValue) => {
    console.log(newValue, oldValue, 'watch')
    if(newValue == 20) alert('way to go !! you maid it to 20 !!')
  })

  const oddOrEven = computed(() => {
    return counterData.count % 2 === 0 ? 'even' : 'odd'
  });

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

  //another mounted hook; this time for counter
  onMounted(() => {
    console.log('do stuff related to counter')
  })


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