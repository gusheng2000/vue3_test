<template>
    <div class="person">
        姓:<input type="text" v-model="firstName"> <br>
        名:<input type="text" v-model="lastName"><br>
        <!-- <span>全名: {{firstName.slice(0,1).toUpperCase()+firstName.slice(1)}} -{{lastName}}</span> -->
        <span>全名: {{fullName}}</span> <br>
        <button @click="changeName">将fullName修改为li-si</button>
    </div>
</template>

<script setup lang="ts" name="Person"> 
    import {ref,computed} from 'vue'
    let firstName= ref('zhang')
    let lastName= ref('san') 
    //计算属性依赖的数据变化了就会从新计算 会缓存
    //这样定义的计算属性 不可以修改
    // let fullName = computed(()=>{
    //     return firstName.value.slice(0,1).toUpperCase()+firstName.value.slice(1)+'-'+lastName.value
    // })


    //这种写法可以改
    let fullName = computed({
        get(){
            return firstName.value.slice(0,1).toUpperCase()+firstName.value.slice(1)+'-'+lastName.value
        },
        set(val){
               const [str1,str2]= val.split('-')
               console.log(str1,str2);
                firstName.value=str1
                lastName.value=str2
        }
    })


    function changeName(){
        console.log(fullName.value);
        fullName.value='li-si'
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