<script setup> 
  /*
    imports 
  */
  import {ref} from 'vue'
  /*
    posts
  */
  const posts = ref([
    {
      id: 'id1',
      title: 'post 1',
      content: 'post 1 content'
    },
    {
      id: 'id2',
      title: 'post 2',
      content: 'post 2 content'
    },
    {
      id: 'id3',
      title: 'post 3',
      content: 'post 3 content'
    }
  ])
</script>
<template>
  <div class="about">
   <h1>Posts</h1>


   <ul>
    <li v-for="post in posts" :key="post.id">
      <RouterLink :to="`/postsDetail/${post.id}`">{{ post.title }}</RouterLink>
    </li>
   </ul>
   <textarea />
  </div>
 </template>
 
