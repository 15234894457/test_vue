<!-- 视图层 -->
<template>   
  <div>
    <div>
        <el-container text-color="#fff" background-color="#545c64" active-text-color="#ffd04b">
          <el-header style="font-size: 33px;">
              <el-button type="primary" circle @click="collapseStatus" class="el-icon-s-home"></el-button>
              <span style="margin-left: 93%;" >王小虎</span>
            </el-header>
        </el-container>
    </div>
    <div>
        <el-container>
          <div>
            <el-menu :collapse="isCollapse">
                <el-submenu index="1">
                  <template slot="title">
                    <i class="el-icon-location"></i>
                    <span slot="title">导航一</span>
                  </template>
                  <el-menu-item-group>
                    <span slot="title">分组一</span>
                    <el-menu-item index="1-1">选项1</el-menu-item>
                    <el-menu-item index="1-2">选项2</el-menu-item>
                  </el-menu-item-group>
                  <el-menu-item-group title="分组2">
                    <el-menu-item index="1-3">选项3</el-menu-item>
                  </el-menu-item-group>
                  <el-submenu index="1-4">
                    <span slot="title">选项4</span>
                    <el-menu-item index="1-4-1">选项1</el-menu-item>
                  </el-submenu>
                </el-submenu>
                <el-menu-item index="2">
                  <i class="el-icon-menu"></i>
                  <span slot="title">导航二</span>
                </el-menu-item>
                <el-menu-item index="3">
                  <i class="el-icon-document"></i>
                  <span slot="title">导航三</span>
                </el-menu-item>
                <el-menu-item index="4">
                  <i class="el-icon-setting"></i>
                  <span slot="title">导航四</span>
                </el-menu-item>
            </el-menu>
            </div>
            <div>
              <el-table
                :data="tableData"
                style="width: 100%">
                <el-table-column
                  prop="date"
                  label="日期"
                  width="180">
                </el-table-column>
                <el-table-column
                  prop="name"
                  label="姓名"
                  width="180">
                </el-table-column>
                <el-table-column
                  prop="address"
                  label="地址">
                </el-table-column>
              </el-table>
            </div>
        </el-container>
    </div>
  </div>
</template>
<script>
export default {
    data() {
        return { 
          tableData: [{
            date: '2016-05-02',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1518 弄'
          }, {
            date: '2016-05-04',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1517 弄'
          }, {
            date: '2016-05-01',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1519 弄'
          }, {
            date: '2016-05-03',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1516 弄'
          }],
            collapseBtnClick: false,
            isCollapse: true,
        }
    },
    methods: {
        collapseStatus() {
            this.collapseBtnClick = this.isCollapse;
            this.isCollapse = !this.isCollapse;
        }
    }
}
</script>

