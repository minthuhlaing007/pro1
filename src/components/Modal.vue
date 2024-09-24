<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{success:theme==='success',danger:theme==='delete'}">
      <slot/>
    </div>
  </div>
</template>

<script>
export default {
  props:["theme"],
  methods:{
    closeModal(){
      this.$emit("close");
    }
  }

}
</script>
<style lang="css" scoped>
.backdrop{
  width:100%;
  height:100%;
  background: rgba(0,0,0,0.5);
  position:fixed;
  top:0;
}
.modal{
  width:500px;
  padding: 20px;
  margin: 200px auto;
  background: #fff;
  border-radius: 15px;
}
.success{
  background: green;
  color: white;
}
.danger{
  background:red;
  color:#fff;
}
</style>