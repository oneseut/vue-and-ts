<script setup  >
import { ref } from 'vue';
import tablelistfrom from './tablelistfrom.vue';
const tableData =ref( [
  {
    date: '2016-05-04',
    name: 'Aleyna Kutzner',
    address: 'Lohrbergstr. 86c, Süd Lilli, Saarland',
  },
  {
    date: '2016-05-03',
    name: 'Helen Jacobi',
    address: '760 A Street, South Frankfield, Illinois',
  },
  {
    date: '2016-05-02',
    name: 'Brandon Deckert',
    address: 'Arnold-Ohletz-Str. 41a, Alt Malinascheid, Thüringen',
  },
  {
    date: '2016-05-01',
    name: 'Margie Smith',
    address: '23618 Windsor Drive, West Ricardoview, Idaho',
  },
])
import {
  Check,
  Delete,
  Edit,
  Message,
  Search,
  Star,
} from '@element-plus/icons-vue'

const deleteRow = (index) => {
  tableData.value.splice(index, 1)
}
const eit = ref(null)

const changetable= (row,index)=>{
  if(eit.value!==null)
  eit.value.open(row,index)
}
const dialogVisible=ref(true)
const datachange= (from,index)=>{
  console.log(from,666,index)
tableData.value[index].name=from.name
tableData.value[index].address=from.address
}
</script>


<template>
<el-table :data="tableData" style="width: 100%;">
<el-table-column prop="date" label="日期" widht="120"/>
<el-table-column prop="name" label="姓名" widht="120"/>
<el-table-column prop="address" label="地址" widht="120"/>
<!-- <el-table-column> 
    <template>
    <el-button type="primary" size="small" >编辑</el-button>
    <template/>
</el-table-column> -->
<el-table-column label="操作" min-width="120">
<template #default="scope">
    <el-button
          type="primary"
          size="small"
          :icon="Edit"
          @click="changetable(scope.row,scope.$index)"
        >
          编辑
        </el-button>
        <el-button
          type="danger"
          size="small"
          :icon="Delete"
           @click.prevent="deleteRow(scope.$index)"
        >
          删除
        </el-button>
      </template>
    </el-table-column>
</el-table>
<!-- <el-dialog title="" v-model="dialogVisible" width="500" >
    <div>
    
    </div>
    <div slot="footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
    </div>
</el-dialog> -->

<tablelistfrom ref="eit" @data-change="datachange"/>
</template>


<style scoped>

</style>