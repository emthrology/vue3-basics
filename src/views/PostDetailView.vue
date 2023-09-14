 
 <script setup>
  import { useRoute, useRouter } from 'vue-router';

  const route = useRoute();
  const router = useRouter();

  const showPostId = () => {
    alert(route.params.id)
  }

  const homeInThreeSec = () => {
    setTimeout(() => {
      router.push('/')
    }, 3000)
  }
 </script>

<template>
  <div class="post-detail">
   <h1>this is a post {{ $route.params.id }} page</h1>
   <div>
    <button @click="showPostId">show post id</button>
   </div>
   <div>
    <button @click="homeInThreeSec">go home in 3 sec.</button>
   </div>
    <p><RouterLink to="/posts">&lt; Back</RouterLink></p>
  </div>
 </template>
