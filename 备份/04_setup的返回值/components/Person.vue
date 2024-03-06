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
  setup(props) {

      // console.log(this); vue3中的this是undefined类型
      //setup执行时间比create还要早

      //数据   此时的数据还不是响应式数据
      let name='张三' 
      let age= 18
      let tel= 15856215010


      //方法
      function changeName(){
        console.log(name);
        name='zhang-san'
        console.log(name);

      }
      function changeAge(){
          this.age++
      }
      function showTel(){
          alert(tel)
      }
    //将数据,方法交出去 模版才可以用
    return{
        name,age,changeAge, changeName, showTel,
    }

    //返回一个渲染函数 内容就是渲染的内容 不常用
    // return ()=>'哈哈'
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