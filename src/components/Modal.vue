<template>
<button @click="modalOpen = true">Show Modal</button>
  <div v-if="modalOpen" class="modal-overlay">
    <div class="modal">
      <div class="modal-header">
        This is a modal
      </div>
      <div class="modal-body">
        Lorem Ipsum
      </div>
      <div class="modal-footer">
        <button @click="modalOpen = false">close</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      modalOpen: false
    }
  }
}
</script>

<style>
  .modal-overlay{
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background: black;
    content: ""
  }
  .modal{
    background: white;
    border: 1px solid black;
    position: fixed;
    top: 50%;
    left:50%;
    transform: translate(-50%, -50%);
  }
  .modal-header{
    border-bottom: 1px solid grey
  }
  .modal-body, .modal-header, .modal-footer{
    padding: 10px
  }
</style>