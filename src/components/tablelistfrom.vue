<template>
<el-dialog title="" v-model="dialogVisible" width="500" >
    <div>
      <el-form label-width="400">
        <el-form-item label="姓名" label-width="50">
        <el-input v-model="from.name"/>
      </el-form-item>
      <el-form-item label="地址" label-width="50">
        <el-input v-model="from.address"/>
      </el-form-item>
    </el-form>
    </div>
    <div slot="footer" style="margin-left: 320px;">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="changedate(from,sonindex)">确 定</el-button>
    </div>
</el-dialog>


</template>
<script setup>
import { ref } from 'vue'
const emit = defineEmits(['data-change'])
const dialogVisible=ref(false)
const from=ref({ 
  name:'',
  address:''
})
let sonindex =null
const open = (row,index)=>{
  console.log(row)
  from.value.name=row.name
  from.value.address=row.address
  sonindex=index
  dialogVisible.value=true
}
const changedate = (from,index)=>{
  emit('data-change',from,index)
  dialogVisible.value=false
}
defineExpose({
  open
})
</script>