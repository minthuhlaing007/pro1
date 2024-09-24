<template>
  <teleport to=".modal" v-if="showModal">
    <Modal :theme='theme' @close="showModal=false">
    <h1>Welcome to my Page</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Porro eligendi nam assumenda quisquam adipisci architecto tempora, eos rerum amet laboriosam, non, vero impedit quas totam vitae quos placeat omnis corrupti.</p>
  </Modal>
  </teleport>

   <teleport to=".modal" v-if="deleteModal">
    <Modal theme="delete" @close="deleteModal=false">
    <h1>Are you sure you want to delete</h1>
    <p>Bye see you soon</p>
  </Modal>
  </teleport>
  <button @click="showModal=true">Show Modal</button>
  <button @click="deleteModal = true">Delete Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue"
export default {
  data(){
    return{
      showModal:false,
      theme:"success",
      deleteModal:false,
    }
  },
components:{
  Modal
}
}
</script>

<style lang="css" scoped>
</style>