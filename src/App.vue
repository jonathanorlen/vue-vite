<template>
  <HelloWorld/>
  <!-- <Suspense>
      <template #default>
        <div>
          
        <Users/>
  <hr>
  <Posts/>
        </div>
      </template>
      <template #fallback>
        <div>Loading..</div>
      </template>
  </Suspense> -->
  
  <teleport to="#destination">
    <Modal/>
  </teleport>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'
import Posts from './components/Posts.vue'
import Users from './components/Users.vue'
import Modal from './components/Modal.vue'
export default {
  components: {
    Posts,
    Users,
    Modal
  },
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