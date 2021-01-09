<template>
 
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