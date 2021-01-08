<template>
  <div v-if="loading">
    Loading
  </div>
  <div v-for="user in users" :key="user.id">
    <div>{{user.name}}</div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data(){
    return{
      users: [],
      loading: false
    }
  },

  methods: {
    async getUsers() {
      this.loading = true
      try{
        let {data} = await axios.get('https://jsonplaceholder.typicode.com/users')
        this.users = data;
        this.loading = false
      }catch(e) {
        this.loading = true
      }
    }
  },

  mounted(){
    this.getUsers()
  }
}
</script>