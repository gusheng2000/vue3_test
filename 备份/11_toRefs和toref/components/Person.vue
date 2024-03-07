<template>
    <div class="person">
        <h1>姓名:{{name}}</h1>
        <h1>姓名:{{age}}</h1>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>

    </div>
</template>

<script setup lang="ts" name="Person"> 
    import {reactive,toRefs,toRef} from 'vue'
    //data
    let person = reactive({
        name: '张三',
        age: 18
    })
    //解构
    // let {name,age}=person
    //torefs  把reactive修饰的对象的所有属性转换为ref修饰的响应式数据
      let {name,age}=toRefs(person)
    //toref  把reactive修饰的对象的一个属性转换为ref修饰的响应式数据
      let nl=toRef(person,age)
    // function
    function changeName(){
        name.value +='~'
        //通过解构的数据就不会响应式的了
        console.log(name,person.name);
    }

    function changeAge(){
        age.value +=1
    } 
</script>
<style>
    .person {
        background-color: #a7aaad;
        box-shadow: 00 10px;
        border-radius: 10px;
        padding: 20px;
    }
    
    button {
        margin: 0 5px;
    }
</style>