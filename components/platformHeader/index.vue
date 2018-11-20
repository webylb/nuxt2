<template>
  <el-row>
    <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
      <div class="platfrom-header warp">
        <div class="container">
          <div class="header-logo">
            <nuxt-link to="/" class="logo-link">
              <img src="image/logo.png" alt="logo">
            </nuxt-link>
          </div>
          <div class="header-menu">
            <div class="menu-item">
              <nuxt-link to="/" class="menu-item-link">首页</nuxt-link>
            </div>
            <div class="menu-item">
              <nuxt-link to="/mall" class="menu-item-link">商城</nuxt-link>
            </div>
            <div class="menu-item">
              <nuxt-link to="/plant" class="menu-item-link">加工厂</nuxt-link>
            </div>
            <div class="menu-item">
              <nuxt-link to="/login" class="menu-item-link">登陆</nuxt-link>
              /
              <nuxt-link to="/register" class="menu-item-link">注册</nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </el-col>
  </el-row>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: '1',
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    }
  }
}
</script>

<style lang="less" scoped>
.platfrom-header {
  height: 70px;
  .container {
    height: 100%;
    display: -webkit-box;
    display: -webkit-flex;
    display: -ms-flexbox;
    display: flex;
    justify-content: space-between;
    -webkit-justify-content: space-between;
    -moz-justify-content: space-between;
    -ms-justify-content: space-between;
    -o-justify-content: space-between;
    .header-logo {
      height: 45px;
      margin-top: 13px;
      .logo-link {
        height: 100%;
        display: block;
        img {
          height: 100%;
        }
      }
    }
    .header-menu {
      height: 100%;
      display: -webkit-box;
      display: -webkit-flex;
      display: -ms-flexbox;
      display: flex;
      justify-content: space-between;
      -webkit-justify-content: space-between;
      -moz-justify-content: space-between;
      -ms-justify-content: space-between;
      -o-justify-content: space-between;
      .menu-item {
        padding: 0 15px;
        height: 100%;
        display: block;
        line-height: 70px;
        font-size: 20px;
        margin-right: 40px;
        &:last-child {
          margin-right: 0;
          font-size: 18px;
        }
        .menu-item-link {
          color: #333;
        }
      }
    }
  }
}
</style>

