<template>
    <div class="post">
        <div v-for="post in posts" :key="post.id">
            <SinglePost :post="post" />
        </div>
    </div>
  </template>
  
  <script>
  import { onMounted, onUnmounted, onUpdated } from 'vue';
import SinglePost from './SinglePost.vue'
  
  export default {
    name: 'PostList',
    props: ['posts'],
    components: { SinglePost }
  }
  </script>
  