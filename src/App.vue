<template>
  <div id="app">
    <el-container>
      <el-header height="">
        <div class="avatar">
          <img src="./assets/images/header/avatar.jpg" alt="" />
        </div>
        <div class="search">
          <i class="el-icon-search"></i>
        </div>
        <el-input
          v-model="input"
          placeholder="Search for year or work"
          class="searchInput"
        ></el-input>
      </el-header>
      <el-container>
        <!-- 侧边栏 -->
        <el-aside width="200px">
          <el-menu default-active="home" router>
            <el-menu-item
              v-for="item in asideBar"
              :key="item.index"
              :index="item.index"
            >
              <i :class="item.icon"></i>
              <span slot="title">{{ item.title }}</span>
            </el-menu-item>
          </el-menu>
        </el-aside>
        <!-- 内容展示部分 -->
        <el-main height="200px" class="main">
          <router-view></router-view>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      input: '',
      asideBar: [
        {
          index: 'home',
          icon: 'el-icon-s-home',
          title: '首页'
        },
        {
          index: 'project',
          icon: 'el-icon-setting',
          title: '项目'
        }
      ]
    };
  },
  methods: {}
};
</script>
<style lang="scss">
.el-container .el-header {
  display: flex;
  padding: 0 0 15px 0;
  align-items: center;
  .avatar {
    width: 200px;
    flex-shrink: 0;
  }
  .avatar img {
    border-radius: 50%;
    height: 50px;
  }
  .search {
    margin-left: 20px;
    color: #a2abc7;
  }
  .searchInput input {
    background-color: #eceef8;
    border: none;
  }
}
.el-aside {
  .el-menu {
    background-color: #eceef8;
    border: none;
  }
  @mixin item($color) {
    color: $color;
    i {
      color: $color;
    }
  }
  .el-menu-item {
    border-radius: 10px;
    font-size: 14px;
    font-weight: bold;
    @include item(#a8b0ca);
    &:hover {
      background-color: #ffffff;
      @include item(#4c5ece);
    }
    &.is-active {
      background-color: white;
      @include item(#4c5ece);
    }
  }
}
.el-main.main {
  padding: 0;
  margin-left: 20px;
}
</style>

