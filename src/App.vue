<script setup >
import { isElementAccessChain } from 'typescript';
import person from './components/person.vue';
import tablelist from './components/tablelist.vue';
const items = [1,2,3,4,5,6]
let flat = false
function changeflat(){
    flat= flat?false:true
    console.log(flat)
}
</script>
<template>
<person/>
<div class="li_text">
    <!-- <ul>
    <li v-for="item in items">{{ item }}<150p
</ul>
<h2 v-if="flat" >显示</h2><br>
<button @click="changeflat">修改显示</button> -->
<div class="flex" style="background-color: brown;">
<p>flex1</p>
</div>
<div class="flex" style="background-color: wheat;">
<p>flex2</p>
</div>
<div class="flex" style="background-color: blue;">
<p>flex3</p>
</div>

</div>
<div style="border-radius: 10px; width: 95%; margin: 10px auto; box-shadow: 0 0 10px; padding: 5px;">
    <tablelist/>
</div>
</template>
<style scoped>
.li_text{
    display: flex;
    /* flex-direction: column; */
    justify-content: space-between;
    background-color: aquamarine;
    border-radius: 5px;
    padding: 15px;
    margin-top: 15px;
    box-shadow:0 0 10px;
}
.flex{
    border-radius: 5px;box-shadow: 0 0 10px;width: 150px;height:150px;text-align: center;
    flex-grow: 1;
}

</style>
