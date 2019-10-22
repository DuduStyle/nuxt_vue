<template>
  <div class="header">
    <logo />
    <!-- 右侧菜单栏 -->
    <div class="header-right">
      <el-menu
        :default-active="activeIndex"
        class="el-menu-demo"
        mode="horizontal"
        @select="handleSelect"
      >
        <el-menu-item index="1">
          首页
        </el-menu-item>
        <el-menu-item index="2">
          案例
        </el-menu-item>
        <el-menu-item index="3">
          服务范围
        </el-menu-item>
        <el-submenu index="4">
          <template slot="title">
            关于
          </template>
          <el-menu-item index="4-1">
            关于我们
          </el-menu-item>
          <el-menu-item index="4-2">
            资讯新闻
          </el-menu-item>
        </el-submenu>
        <el-menu-item index="5">
          <a href="https://www.ele.me" target="_blank">联系</a>
        </el-menu-item>
      </el-menu>
    </div>
  </div>
</template>
<script>
import Logo from "./logo.vue";
export default {
  components: {
    Logo
  },
  data() {
    return {
      activeIndex: "1",
      activeIndex2: "1"
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    }
  }
};
</script>

<style >
.header {
  background:rgba(34, 34, 34, 0);
  padding: 0 4%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
}
.el-menu.el-menu--horizontal {
  border-bottom: 0 none;
}
.el-menu--horizontal > .el-menu-item {
  color: #fff;
}
.el-menu--horizontal > .el-menu-item.is-active {
  color: #fff;
}
.el-menu--horizontal > .el-submenu .el-submenu__title {
  color: #fff;
}
.el-menu {
  background: transparent;
}
</style>
