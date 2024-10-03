<template>
<div  class="person">
    <h2>姓名:{{ name }}</h2>
    <h2>年龄:{{ age }}</h2>
    <h2>电话:{{ tel }}</h2>
    <button @click="changename">修改名字</button>
    <button @click="changeage">修改年龄</button>
    <button @click="changetel">修改电话</button>
</div>
</template>
<script lang="ts">
  export default {//此处语法检查严格要求有一个空白分隔符
  name:'person'
} 
</script>
 <script setup lang="ts">
import { ref } from 'vue';

let name = ref('张三')
let age = 18
let tel = '18475996255'
function changename(){
  name.value='zhangsan'
}
function changeage(){
  age = 19
}
function changetel()
{
  tel='14578555422'
}
</script>
<style scoped>
.person{
    background-color: aqua;
    box-shadow: 0 0 10px;
    border-radius: 5px;
    padding: 20px;
} 
</style>