<template>
      <el-container>
        <el-header>
          <div>
            <h2 class="header">binLog</h2>
          </div>
        </el-header>
        <el-container>
          <el-aside width="200px">
            <el-menu  router default-active="clientList">
              <el-submenu index="">
                <template slot="title">
                  <i class="el-icon-menu"></i>
                  <span>应用管理</span></template>
                <el-menu-item index="clientList" route="">应用列表</el-menu-item>
                <el-menu-item index="addClient" route="" >新增应用</el-menu-item>
              </el-submenu>
              <el-menu-item index="queueMonitoring" route="" >队列监控</el-menu-item>
              <el-menu-item index="logProgress" route="" >日志进度</el-menu-item>
            </el-menu>
          </el-aside>
          <el-main>
            <el-col :span="24" class="breadcrumb-container">
              <strong class="title">
                <el-breadcrumb separator="/" class="breadcrumb-inner" style="float: left">
                  <el-breadcrumb-item v-for="item in $route.matched" :key="item.path">
                    {{ item.name }}
                  </el-breadcrumb-item>
                </el-breadcrumb>
              </strong>
            </el-col>
            <el-col :span="24" class="content-wrapper" style="margin-top: 10px">
              <transition name="fade" mode="out-in">
                <router-view></router-view>
              </transition>
            </el-col>
          </el-main>
        </el-container>
      </el-container>
</template>
<script>


</script>
<style>
  .header{
    text-align: left;margin-top: 5px;
    font-family: Garamond;
    font-size: 40px;
    margin-left: 20px;
  }
  .el-header{
    /*background-color: #B3C0D1;*/
    /*color: #333;*/
    text-align: center;
    line-height: 60px;
    position: absolute;
    width: 100%;
    top: 0px;
    right: 0px;
  }

  .el-aside {
    /*background-color: #D3DCE6;*/
    /*color: #333;*/
    text-align: center;
    line-height: 200px;
    top: 60px;
    position: absolute;
    left: 0px;
    bottom: 0px;
  }

  .el-main {
    /*background-color: #E9EEF3;*/
    /*color: #333;*/
    text-align: center;
    /*line-height: 300px;*/
    position: absolute;
    bottom: 0px;
    top: 60px;
    left: 200px;
    right: 0px;
  }
</style>
