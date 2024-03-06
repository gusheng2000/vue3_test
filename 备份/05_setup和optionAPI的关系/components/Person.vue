<template>
  <div class="person">
    <h2>姓名: {{name}}</h2>
    <h2>姓名: {{age}}</h2>
    <button @click="changeName">更改姓名</button>
    <button @click="changeAge">更改年龄</button>
    <button @click="showTel">查看联系方式</button>
    <hr>

    <h2>测试 {{a}}</h2>
    <h2>date读取setup里的name: {{c}}</h2>
    <!-- <h2>setup读取date里的数据{{x}}</h2> -->
    <button @click="b">methons方法</button>
  </div>
</template>

<script lang="ts">
  /**
   * vue2的语法可以读取vue语法的数据  ,vue3不能读取不vue2数据的写法
   * 
   * **/
export default{
  name: 'Person',
  data() {
    return {
      a: 100,
      c: this.name,
      x: 900
    }
  },
  methods: {
    b(){
      alert('b')
    }
  },
  setup() {
      let name='张三' 
      let age= 18
      let tel= 15856215010
      // let x=d   let x=this.d  错误写法
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