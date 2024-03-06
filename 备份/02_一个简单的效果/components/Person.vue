<template>
  <div class="person">
    <h2>姓名: {{name}}</h2>
    <h2>姓名: {{age}}</h2>
    <button @click="changeName">更改姓名</button>
    <button @click="changeAge">更改年龄</button>
    <button @click="showTel">查看联系方式</button>
  </div>
</template>

<script lang="ts">
  /**
   * 1.vue3可以使用vue2语法 optionAPI(配置式)
   * 2.vue新的语法api是 compositionAPI(组合式)
   * **/
export default{
  name: 'Person',
  data(){
    return{
      name: '张三',
      age: 18,
      tel: 15856215010
    }
   },
   methods: {
    showTel(){
      alert(this.tel)
    },
    changeName(){
      this.name='zhang-san'
    },
     changeAge(){
      this.age++
    },
   },
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