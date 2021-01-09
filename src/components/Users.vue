<template>
  <div v-for="user in users.data" :key="user.id">
    <div>{{user.name}}</div>
  </div>
</template>

<script>
import axios from 'axios'
export default {

     async setup(){
          let users = await axios.get('https://jsonplaceholder.typicode.com/users')
          return {
               users
          }
     }
}
</script>