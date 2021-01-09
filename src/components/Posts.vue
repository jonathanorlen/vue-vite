<template>
  <div v-for="post in posts.data" :key="post.id">
    <div>{{post.title}}</div>
  </div>
</template>

<script>
import axios from 'axios'
export default {

     async setup(){
          let posts = await axios.get('https://jsonplaceholder.typicode.com/posts')
          return {
               posts
          }
     }
}
</script>