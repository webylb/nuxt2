<template>
  <section class="mall wrap">
    <mallHeader/>
    <section class="mall-content-banner" />
    <div class="container">
      <el-container>
        <el-aside width="200px">
          <el-row class="tac">
            <el-col :span="24">
              <el-menu
                default-active="2-1"
                class="el-menu-vertical-demo"
                @open="handleOpen"
                @close="handleClose">
                <el-menu-item index="1">
                  <span slot="title">全部产品</span>
                </el-menu-item>
                <el-submenu index="2">
                  <template slot="title">
                    <span>扩展产品(12)</span>
                  </template>
                  <el-menu-item index="2-1">-T恤(3)</el-menu-item>
                  <el-menu-item index="2-2">-卫衣(3)</el-menu-item>
                  <el-menu-item index="2-3">-帆布袋(3)</el-menu-item>
                  <el-menu-item index="2-4">-抱枕(3)</el-menu-item>
                </el-submenu>
                <el-menu-item index="3">
                  <span slot="title">办公用品</span>
                </el-menu-item>
                <el-menu-item index="4">
                  <span slot="title">节日礼品</span>
                </el-menu-item>
                <el-menu-item index="5">
                  <span slot="title">团队服饰</span>
                </el-menu-item>
                <el-menu-item index="6">
                  <span slot="title">体育运动</span>
                </el-menu-item>
              </el-menu>
            </el-col>
          </el-row>
        </el-aside>
        <el-main>
          <el-breadcrumb separator-class="el-icon-arrow-right" class="categoryBreadcrumb">
            <el-breadcrumb-item v-for="(item,index) in categoryBreadcrumb" :key="index" :to="{ path: item.link }">{{ item.name }}</el-breadcrumb-item>
          </el-breadcrumb>
          <section v-for="(item,index) in mallCategory" :key="index" class="hot-gift">
            <div class="gift-list">
              <div v-for="(term,index) in item.categoryList" :key="index" class="gift-item">
                <nuxt-link :to="term.link">
                  <img :src="term.img" :alt="term.alt">
                  <p v-if="term.name">{{ term.name }}</p>
                </nuxt-link>
              </div>
            </div>
          </section>
          <div style="float:right;margin-top:20px;">
            <el-pagination
              :current-page="currentPage"
              :page-sizes="[20, 40, 80, 100]"
              :page-size="20"
              :total="200"
              layout="total, sizes, prev, pager, next, jumper"
              @size-change="handleSizeChange"
              @current-change="handleCurrentChange" />
          </div>
        </el-main>
      </el-container>
    </div>
    <mallFooter/>
  </section>
</template>

<script>
import mallHeader from '~/components/mallHeader'

export default {
  name: "Mall",
  components: {
    mallHeader,
    mallFooter: () => import('@/components/mallFooter'),
  },
  data(){
    return {
      categoryBreadcrumb: [
        {name:'全部产品',link:"/mall/category"},
        {name:"扩展产品",link:"/mall/category"},
        {name:"T恤",link:"/mall/category"}
      ],
      mallCategory: [
        {
          categoryList : [{img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"},
          {img:"/image/category-img.jpg",name:"男士圆领T恤",alt:"hot-gift",link:"/mall"}]
        }
      ],
      currentPage: 1
    }
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    handleSizeChange(val) {
      console.log(`每页 ${val} 条`);
    },
    handleCurrentChange(val) {
      console.log(`当前页: ${val}`);
    }
  }
}
</script>

<style lang="less" scoped>
.mall {
  .mall-content-banner {
    background:url("/image/mall-banner.jpg") no-repeat center;
    background-size: auto;
    height: 600px;
  }
  .el-aside {
    padding-top: 105px;
    .el-menu {
      border-right: 0;
      .el-submenu {
        span {
          font-size: 18px;
        }
      }
      .el-menu-item {
        font-size: 18px;
      }
    }
  }
  .categoryBreadcrumb {
    height: 45px;
    line-height: 45px;
    background-color: #ebebeb;
    padding: 0 10px;
    border-radius: 4px;
  }
  .hot-gift {
    padding: 30px 0;
    .gift-list {
      display: -webkit-box;
      display: -webkit-flex;
      display: -ms-flexbox;
      display: flex;
      justify-content: space-between;
      -webkit-justify-content: space-between;
      -moz-justify-content: space-between;
      -ms-justify-content: space-between;
      -o-justify-content: space-between;
      flex-wrap: wrap;
      -webkit-flex-wrap: wrap;
      -moz-flex-wrap: wrap;
      -ms-flex-wrap: wrap;
      -o-flex-wrap: wrap;
      .gift-item {
        // width: 271px;
        // height: 271px;
        margin: 10px 0;
        img {
          width: 100%;
          height: auto;
        }
        p {
          color: #333;
        }
      }
    }
  }
}
</style>

