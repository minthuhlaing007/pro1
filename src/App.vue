<template>
  <div v-if="showModal">
    <Modal :theme='theme' @close="showModal=false">
    <h1>Hello World</h1>
    <h3>My name is John Doe</h3>
    <p>Lorem ipsum dolor sit, amet consectetur, adipisicing elit. Ipsum ea amet minus, ullam earum omnis in, quidem, at beatae tenetur iure veritatis ad sapiente. Adipisci asperiores labore voluptatibus, commodi similique.</p>
    <template v-slot:ul>
      <ul>
        <li>One </li>
        <li>Two </li>
        <li>Three </li>
        <li>Four</li>
      </ul>
    </template>
  </Modal>
  </div>
  <div v-if="deleteModal">
    <Modal :themeone='themeone' @delete="deleteModal=false">
    <h1>Are you sure you want to Delete</h1>
    <h3>Get the fuck out of my Page</h3>
    <p>FUCK YOU</p>
    <template v-slot:ul>
      <ul>
        <li>One </li>
        <li>Two </li>
        <li>Three </li>
        <li>Four</li>
      </ul>
    </template>
  </Modal>
  </div>
  <button @click="showModal=true">Login Modal</button>
  <button @click="deleteModal=true">Delete Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue"
export default {
  data(){
    return{
      theme:"success",
      showModal:false,
      themeone:"delete",
      deleteModal: false
    }
  },
components:{
  Modal
}
}
</script>

<style lang="css" scoped>
</style>