<template>
  <div class="app">
    <h1>你好啊！</h1>
    <person />
  </div>
</template>

<script lang="ts">
  import Person from './components/Person.vue'
  export default{
      name: 'App',
      components:{
        Person
      }
  }
</script>
<style>
.app{
  background-color:#ddd;
  box-shadow:00 10px;
  border-radius:10px;
  padding:20px;   
}
</style>