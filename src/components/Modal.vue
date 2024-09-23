<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{success:theme==='success'}">
      <slot/>
      <slot name="ul" />
    </div>
  </div>
   <div class="backdrop" @click.self="deleteModal">
    <div class="modal" :class="{danger:themeone==='delete'}">
      <slot/>
      <slot name="ul" />
    </div>
  </div>
</template>

<script>
export default {
props:["theme","themeone"],
methods:{
  closeModal(){
    this.$emit("close");
  },
  deleteModal(){
    this.$emit("delete");
  }
}
}
</script>

<style lang="css" scoped>
.backdrop{
  width:100%;
  height:100%;
  background:rgba(0,0,0,0.5);
  position:fixed;
  top:0;
}
.modal{
  padding:20px;
  margin:200px auto;
  width:800px;
  background:white;
  border-radius:20px;
}
.success{
  background: green;
  color: white
}
.danger{
  background: darkred;
  color: white
}
</style>