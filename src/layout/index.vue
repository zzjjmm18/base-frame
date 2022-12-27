<template>
  <el-container class="container">
    <el-header>
      <div class="title">
        <span>耐视特</span>
        <hamburger :is-active="isCollapse" class="hamburger-container" @toggleClick="toggleSideBar"/>
      </div>
      <div class="header-menu">
        <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
          <el-menu-item index="1">处理中心</el-menu-item>
          <el-menu-item index="2">我的工作台</el-menu-item>
          <el-menu-item index="3">消息中心</el-menu-item>
          <el-menu-item index="4">系统设置</el-menu-item>
        </el-menu>
      </div>
      <div class="info">个人信息展示</div>
    </el-header>
    <el-container class="main-container">
     
        <el-menu
      :default-active="activeIndex2"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose"
      :collapse="isCollapse">
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span>导航一</span>
        </template>
        <el-menu-item-group>
          <template slot="title">分组一</template>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="分组2">
          <el-menu-item index="1-3">选项3</el-menu-item>
        </el-menu-item-group>
        <el-submenu index="1-4">
          <template slot="title">选项4</template>
          <el-menu-item index="1-4-1">选项1</el-menu-item>
        </el-submenu>
      </el-submenu>
      <el-menu-item index="2">
        <i class="el-icon-menu"></i>
        <span slot="title">导航二</span>
      </el-menu-item>
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-location"></i>
          <span>导航一</span>
        </template>
        <el-menu-item-group>
          <template slot="title">分组一</template>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="分组2">
          <el-menu-item index="1-3">选项3</el-menu-item>
        </el-menu-item-group>
        <el-submenu index="1-4">
          <template slot="title">选项4</template>
          <el-menu-item index="1-4-1">选项1</el-menu-item>
        </el-submenu>
      </el-submenu>
      <el-menu-item index="4">
        <i class="el-icon-setting"></i>
        <span slot="title">导航四</span>
      </el-menu-item>
    </el-menu>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
import Hamburger from '@/layout/components/Hamburger.vue'
  export default {
    components: {
      Hamburger
    },
    data() {
      return {
        activeIndex: '1',
        activeIndex2: '1',
        isCollapse: true
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      },
      toggleSideBar() {
        this.isCollapse = !this.isCollapse
      },
    }
  }
</script>

<style scoped lang="less">
.container {
  height: 100%;
}
.el-header {
  display: flex;
  height: 10%;
  justify-content: space-between;
  align-items: center;
  background-color: #37c9ed;

  .title {
    width: 10%;

    .hamburger-container {
    line-height: 46px;
    height: 100%;
    float: right;
    cursor: pointer;
    transition: background .3s;
    -webkit-tap-highlight-color:transparent;

    &:hover {
      background: rgba(0, 0, 0, .025)
    }
  }
  }

  .header-menu {
    width: 70%;
  }

  .info {
    width: 10%;
  }
}
.main-container {
  height: 90%;

  .el-aside {
    background-color: #37c9ed;
  }
}

.el-menu-vertical-demo {
  min-height: 100%;
  background-color: #37c9ed;
}

.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 100%;
  background-color: #37c9ed;
}
</style>