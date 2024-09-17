<template>
<div  class="person">
    <h2>姓名:{{ name }}</h2>
    <h2>年龄:{{ age }}</h2>
    <h2>电话:{{ tel }}</h2>

</div>
</template>
<script>
  export default {//此处语法检查严格要求有一个空白分隔符
  name:'person'
} 
</script>
 <script setup lang="ts">
import { ref } from 'vue';

let name = ref('张三')
let age = 18
let tel = '18475996255'
</script>
<style scoped>
.person{
    background-color: aqua;
    box-shadow: 0 0 10px;
    border-radius: 5px;
    padding: 20px;
} 
</style>