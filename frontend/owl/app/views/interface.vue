<template>
  <el-table
    :data="tableData"
    style="width: 100%"
    height="250"
    stripe
    :row-class-name="tableRowClassName">
    <el-table-column
      prop="name"
      label="接口名称"
      width="180">
    </el-table-column>
    <el-table-column
      prop="path"
      label="接口路径"
      width="180">
    </el-table-column>
    <el-table-column
      prop="describle"
      label="接口描述">
    </el-table-column>
    <el-table-column label="操作" width="400" align='center'>
        <template slot-scope="scope">
          <el-button type='info' size="small" @click="handleInfo(scope.$index, scope.row)" round>详情</el-button>
          <el-button type="danger" size="small" @click="handleDel(scope.$index, scope.row)" round>删除</el-button>
        </template>
      </el-table-column>
  </el-table>
</template>

<style>
  .el-table .warning-row {
    background: oldlace;
  }

  .el-table .success-row {
    background: #f0f9eb;
  }
</style>

<script>
export default {
  methods: {
    tableRowClassName ({row, rowIndex}) {
      if (rowIndex % 2 === 1) {
        return 'warning-row';
      } else {
        return 'success-row';
      }
      return '';
    },
    //删除
    handleDel:function (index ,row) {
      this.$router.push({
          path: '../HelloWorld',
          query: {
            data: row.id
          }
         })
      },
    // 编辑
    handleInfo: function(index ,row){
        this.$router.push({
          path: '../HelloWorld',
          query: {
            data: row.id
          }
         })
      }
  },
  data () {
    return {
      tableData: [{
        name: 'pos获取用户信息',
        path: '／getconfig',
        describle: 'pos获取用户信息'
      }, {
        name: 'pos获取用户信息',
        path: '／getconfig',
        describle: 'pos获取用户信息'
      }, {
        name: 'pos获取用户信息',
        path: '／getconfig',
        describle: 'pos获取用户信息'
      }, {
        name: 'pos获取用户信息',
        path: '／getconfig',
        describle: 'pos获取用户信息'
      }, {
        name: 'pos获取用户信息',
        path: '／getconfig',
        describle: 'pos获取用户信息'
      }, {
        name: 'pos获取用户信息',
        path: '／getconfig',
        describle: 'pos获取用户信息'
      }, {
        name: 'pos获取用户信息',
        path: '／getconfig',
        describle: 'pos获取用户信息'
      }, {
        name: 'pos获取用户信息',
        path: '／getconfig',
        describle: 'pos获取用户信息'
      }]
    }
  }
}
</script>