<template>
<div class="table-box">
  <div class="title">
    <h2>CRUD Demo</h2>
  </div>
  <div class="query-box">
    <el-input v-model="queryInput" placeholder="请输入姓名" />
    <el-button type="primary">增加</el-button>
  </div>
  <el-table :data="tableData"  border style="width: 100%">
    <el-table-column fixed prop="date" label="Date" width="150" />
    <el-table-column prop="name" label="Name" />
    <el-table-column prop="state" label="State"  />
    <el-table-column prop="city" label="City"  />
    <el-table-column prop="address" label="Address"  />
    <el-table-column prop="zip" label="Zip"  />
    <el-table-column fixed="right" label="Operations" width="120">
      <template #default>
        <el-button link type="primary" size="small" @click="handleClick">Detail</el-button>
        <el-button link type="primary" size="small">Edit</el-button>
      </template>
    </el-table-column>
  </el-table>
</div>


</template>

<script  setup>
import {ref} from "vue";
// data
let queryInput = ref("")
let tableData = ref([
  {
    date: '2016-05-03',
    name: 'Tom',
    state: 'California',
    city: 'Los Angeles',
    address: 'No. 189, Grove St, Los Angeles',
    zip: 'CA 90036',
    tag: 'Home',
  },
  {
    date: '2016-05-02',
    name: 'Tom',
    state: 'California',
    city: 'Los Angeles',
    address: 'No. 189, Grove St, Los Angeles',
    zip: 'CA 90036',
    tag: 'Office',
  },
  {
    date: '2016-05-04',
    name: 'Tom',
    state: 'California',
    city: 'Los Angeles',
    address: 'No. 189, Grove St, Los Angeles',
    zip: 'CA 90036',
    tag: 'Home',
  },
  {
    date: '2016-05-01',
    name: 'Tom',
    state: 'California',
    city: 'Los Angeles',
    address: 'No. 189, Grove St, Los Angeles',
    zip: 'CA 90036',
    tag: 'Office',
  },
])

//方法
const handleClick = () => {
  console.log('click')
};

</script>
<style scoped>
.table-box{margin: 5px;padding: 5px;}
.query-box{ width: 100%;}
.query-box input{width:500px; vertical-align: bottom; border: 1px solid red;}
.query-box button{float: right;width:120px;}
</style>
