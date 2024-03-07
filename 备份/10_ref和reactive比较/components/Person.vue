<template>
  <div class="person">
    <h2>汽车信息: 一辆{{car.brand}}汽车,价值{{car.price}}万人民币</h2>
    <button @click="changePrice">更改汽车价格</button>
    <hr>
    <h2>游戏列表</h2>
    <ul>
      <li v-for=" g in games" :key="g.id">{{g.name}}</li>
    </ul>
    <button @click='changeFirstGame'>修改第一个游戏的名字</button>
  </div>
</template>

<script setup lang="ts" name="Person123">
    //ref 修饰响应式对象 支持深层次和浅层次对象,推荐浅层次使用

    import {
        ref,
        reactive
    } from 'vue'

    let car = ref({
        brand: '奔驰',
        price: 100
    })

    let games = ref([{
            id: 'dasdasd01',
            name: '王者荣耀'
        }, {
            id: 'dasdasd02',
            name: '和平精英'
        }, {
            id: 'dasdasd03',
            name: '蛋仔派对'
        }])
        //对象类型为 RefImpl类型它的value属性是Proxy类型
    console.log(car);

    function changePrice() {
        car.value.price += 50
    }

    function changeFirstGame() {
        games.value[0].name = '蝴蝶流星剑'
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