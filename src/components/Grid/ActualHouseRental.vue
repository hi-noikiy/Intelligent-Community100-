<template>
  <div>
    <el-row  class="mainRight">
      <el-col :span="24" class="borderBottom">
        出租房列表
      </el-col>
    </el-row>
    <el-row style="padding-left: 30px;padding-top: 20px;background: #fff;">
      <el-col :span="24" style="text-align: left;">
        <el-form :inline="true" :model="formInline" class="demo-form-inline">
          <el-form-item label="所属网格:">
            <el-input v-model="formInline.network" placeholder="请输入"></el-input>
          </el-form-item>
          <el-form-item label="所属建筑:">
            <el-select v-model="formInline.house" placeholder="请选择">
              <el-option label="衣服加工厂" value="衣服加工厂"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="所属单元:">
            <el-select v-model="formInline.unit" placeholder="请选择">
              <el-option label="一单元" value="一单元"></el-option>
            </el-select>
          </el-form-item>
          <el-form-item label="门牌号:">
            <el-input v-model="formInline.id" placeholder="请输入"></el-input>
          </el-form-item>
          <el-form-item label="智能搜索:">
            <el-input v-model="formInline.search" placeholder="房主姓名/身份证号"></el-input>
          </el-form-item>
          <el-form-item class="search">
            <el-button type="primary" size="small"><img :src="search" alt="" style="margin-right: 8px;">查询</el-button>
            <el-button type="primary" size="small"><img :src="add" alt="" class="add">添加</el-button>
          </el-form-item>
        </el-form>
      </el-col>
    </el-row>
    <el-table
      :data="tableData"
      border
      stripe
      style="width:96%;margin:0 auto"
    >
      <el-table-column
        type="selection"
        width="55">
      </el-table-column>
      <el-table-column
        prop="network"
        label="所属网格"
        show-overflow-tooltip
        min-width="18%">
      </el-table-column>
      <el-table-column
        prop="house"
        label="所属建筑"
        min-width="13%">
      </el-table-column>
      <el-table-column
        prop="unit"
        label="所属单元"
        min-width="12%">
      </el-table-column>

      <el-table-column
        prop="id"
        label="门牌号"
        min-width="12%">
      </el-table-column>
      <el-table-column
        prop="name"
        label="房主姓名"
        min-width="12%">
      </el-table-column>
      <el-table-column
        prop="desc"
        label="住房情况"
        min-width="12%">
      </el-table-column>
      <el-table-column
        fixed="right"
        label="操作"
        min-width="30%">
        <template slot-scope="scope">
          <el-button @click="handleClick(scope.row)"size="small" >详情</el-button>
          <el-button @click="handleClick(scope.row)" size="small">编辑</el-button>
          <el-button @click="deleteRow(scope.$index,tableData)"size="small">移除</el-button>
        </template>
      </el-table-column>
    </el-table>
    <el-row style="background: #fff;padding-bottom:40px;margin-top:200px;">
      <el-col :span="24">
        <div class="block">
          <el-pagination
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            :current-page="currentPage4"
            :page-sizes="[5,10]"
            :page-size="10"
            :page-count="2"
            layout="prev, pager,next, jumper, total, sizes"
            :total="12">
          </el-pagination>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        search:require('../images/search.png'),
        add:require('../images/add.png'),
        formInline: {
          network:'',
          house:'',
          id:'',
          search:''
        },
        currentPage4: 1,
        tableData: [
          {
            network:'新天社区一号网格',
            house:'衣服加工厂',
            unit:'一单元',
            id:'001',
            name:'翁振新',
            desc:'常住',
          },
          {
            network:'新天社区一号网格',
            house:'衣服加工厂',
            unit:'一单元',
            id:'002',
            name:'李小龙',
            desc:'租赁',
          },
          {
            network:'新天社区一号网格',
            house:'衣服加工厂',
            unit:'一单元',
            id:'003',
            name:'吴昊',
            desc:'常住',
          },
          {
            network:'新天社区一号网格',
            house:'衣服加工厂',
            unit:'一单元',
            id:'004',
            name:'李慕云',
            desc:'常住',
          },
          {
            network:'新天社区一号网格',
            house:'衣服加工厂',
            unit:'一单元',
            id:'005',
            name:'范金金',
            desc:'常住',
          },
          {
            network:'新天社区一号网格',
            house:'衣服加工厂',
            unit:'一单元',
            id:'006',
            name:'李柳',
            desc:'常住',
          },
        ],
      }
    },
    methods: {
      onSubmit() {
        console.log('submit!');
      },
      handleClick(row) {
        console.log(row);
      },
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      },
      //删除所选中的一行
      deleteRow(index,rows){
        rows.splice(index,1)
      },
    },
  }
</script>
<style>

</style>
<style scoped>
  .cell .el-button:first-child{
    background: none;
    border:1px solid #999
  }
  .cell .el-button:nth-child(2){
    background: none;
    border:1px solid #ff813d;
    color:#ff813d
  }
  .cell .el-button:nth-child(3){
    background: none;
    border:1px solid #008aff;
    color:#008aff;
  }
</style>
