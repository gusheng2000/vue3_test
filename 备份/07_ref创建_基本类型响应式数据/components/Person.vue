<template>
  <div class="person">
    <h2>姓名: {{name}}</h2>
    <h2>姓名: {{age}}</h2>
    <button @click="changeName">更改姓名</button>
    <button @click="changeAge">更改年龄</button>
    <button @click="showTel">查看联系方式</button>
    <hr>
  </div>
</template>

<script setup lang="ts" name="Person123">
      import {ref} from 'vue'

  
      let name=ref('张三') 
      let age= ref(18)
      let tel= 15856215010

      //方法
      function changeName(){
        console.log(name);
        name.value='zhang-san'
        console.log(name);
      }
      function changeAge(){
          console.log(age);
          age.value++
          console.log(age);

      }
      function showTel(){
          alert(tel)
      }
</script>
<style>
  .person{
      background-color:#545f67;
      box-shadow:00 10px;
      border-radius:10px;
      padding:20px;  
  }
  button{
    margin: 0 5px;
  }
</style>