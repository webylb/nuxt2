<template>
  <el-row>
    <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
      <div class="mall-header warp">
        <div class="container">
          <div class="header-logo">
            <nuxt-link to="/mall" class="logo-link">
              <img src="/image/logo.png" alt="logo">
            </nuxt-link>
          </div>
          <div class="header-menu">
            <div class="menu-item">
              <nuxt-link to="/mall" class="menu-item-link">首页</nuxt-link>
            </div>
            <div class="menu-item">
              <a class="menu-item-link" @click="applyAdd(1)">扩展活动</a>
            </div>
            <div class="menu-item">
              <a class="menu-item-link" @click="applyAdd(2)">办公用品</a>
            </div>
            <div class="menu-item">
              <a class="menu-item-link" @click="applyAdd(3)">节日礼品</a>
            </div>
            <div class="menu-item">
              <a class="menu-item-link" @click="applyAdd(4)">团体服饰</a>
            </div>
            <div class="menu-item">
              <a class="menu-item-link" @click="applyAdd(5)">体育运动</a>
            </div>
          </div>
          <div class="header-operation">
            <div class="operation-item">
              <nuxt-link :to="{ name:'mall-shoppingCart-id', params:{ id:'1'}}" class="operation-item-link"><i class="el-icon-goods"/></nuxt-link>
            </div>
            <div class="operation-item">
              <a class="operation-item-link" @click="goLogin">登陆</a>
              |
              <nuxt-link to="/register" class="operation-item-link">注册</nuxt-link>
            </div>
            <div class="operation-item">
              <nuxt-link :to="{ name:'mall-shoppingCart-id', params:{ id:'1'}}" class="operation-item-link">帮助中心</nuxt-link>
            </div>
          </div>
        </div>
      </div>
      <mallLogin v-show="isShowLogin"/>
    </el-col>
  </el-row>
</template>

<script>
// import mallLogin from '~/components/mallLogin'
import { mapState, mapActions, mapMutations } from 'vuex'

export default {
  components: {
    mallLogin: () => import('@/components/mallLogin'),
  },
  data() {
    return {
      // showLogin: false
    };
  },
  computed: {
    ...mapState(['isShowLogin'])
  },
  methods: {
    ...mapMutations(['CHANGE_ISSHOWLOGIN']),
    goLogin(){
      console.log(this.$store.state.isShowLogin);
      this.CHANGE_ISSHOWLOGIN(true)
    },
    applyAdd(params){
      // 用 class="category-jump" 添加锚点
      let jump = document.querySelector('.category-jump'+params);
      let total = jump.offsetTop + window.screen.height;
      let distance = document.documentElement.scrollTop || document.body.scrollTop;
      console.log(total+","+distance);
      // 平滑滚动，时长500ms，每10ms一跳，共50跳
      let step = total / 50;
      if (total > distance) {
        smoothDown()
      } else {
        let newTotal = distance - total;
        step = newTotal / 50;
        smoothUp()
      }
      function smoothDown () {
        if (distance < total) {
          distance += step;
          document.body.scrollTop = distance;
          document.documentElement.scrollTop = distance;
          setTimeout(smoothDown, 10)
        } else {
          document.body.scrollTop = total;
          document.documentElement.scrollTop = total
        }
      }
      function smoothUp () {
        if (distance > total) {
          distance -= step;
          document.body.scrollTop = distance;
          document.documentElement.scrollTop = distance;
          setTimeout(smoothUp, 10)
        } else {
          document.body.scrollTop = total;
          document.documentElement.scrollTop = total
        }
      }
    }
  }
}
</script>

<style lang="less" scoped>
.mall-header {
  -moz-box-shadow:0px 0px 3px #d4bbbb;
  -webkit-box-shadow:0px 0px 3px #d4bbbb;
  box-shadow:0px 0px 3px #d4bbbb;
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
        margin-right: 30px;
        cursor: pointer;
        &:last-child {
          margin-right: 0;
        }
        .menu-item-link {
          color: #333;
        }
      }
    }
    .header-operation {
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
      .operation-item {
        padding: 0 5px;
        height: 30px;
        display: block;
        line-height: 30px;
        font-size: 14px;
        margin-right: 5px;
        cursor: pointer;
        &:last-child {
          margin-right: 0;
        }
        .operation-item-link {
          color: #333;
        }
      }
    }
  }
}
</style>

