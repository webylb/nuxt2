<template>
  <section class="mall wrap">
    <mallHeader/>
    <section class="mall-content-banner" />
    <div class="container">
      <!-- section content -->
      <section v-for="(item,index) in mallCategory" :key="index" class="hot-gift">
        <h2 :class="'category-jump'+(index+1)">{{ item.categoryName }}</h2>
        <div class="gift-list">
          <div v-for="(term,index) in item.categoryList" :key="index" class="gift-item">
            <nuxt-link :to="term.link">
              <img :src="term.img" :alt="term.alt">
              <p v-if="term.name">{{ term.name }}</p>
            </nuxt-link>
          </div>
        </div>
      </section>
      <!-- 合作伙伴 -->
      <section class="mall-partners">
        <h2>合作伙伴</h2>
        <div class="mall-partners-list">
          <div class="mall-partners-item"><img src="/image/mall-p1.png" alt="Alibaba"></div>
          <div class="mall-partners-item"><img src="/image/mall-p2.png" alt="HUAWEI"></div>
          <div class="mall-partners-item"><img src="/image/mall-p3.png" alt="XIAOMI"></div>
          <div class="mall-partners-item"><img src="/image/mall-p4.png" alt="PINGAN"></div>
        </div>
      </section>
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
      mallCategory: [
        {
          categoryName:"热门礼品",
          categoryList : [{img:"/image/hot-gift.jpg",alt:"hot-gift",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",link:"/mall"}]
        },
        {
          categoryName:"扩展活动",
          categoryList : [{img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-banner.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"}]
        },
        {
          categoryName:"办公用品",
          categoryList : [{img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-banner.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"}]
        },
        {
          categoryName:"节日礼品",
          categoryList : [{img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-banner.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"}]
        },
        {
          categoryName:"团队服装",
          categoryList : [{img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-banner.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"}]
        },
        {
          categoryName:"体育运动",
          categoryList : [{img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-banner.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"},
          {img:"/image/hot-gift.jpg",alt:"hot-gift",name:"男士圆领T恤",link:"/mall"}]
        }
      ],
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
  .hot-gift {
    padding: 50px 0;
    h2 {
      margin-bottom: 10px;
      font-size: 30px;
    }
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
  .mall-partners {
    padding: 50px 0;
    h2 {
      margin-bottom: 80px;
      font-size: 30px;
      text-align: center
    }
    .mall-partners-list {
      display: -webkit-box;
      display: -webkit-flex;
      display: -ms-flexbox;
      display: flex;
      justify-content: space-between;
      -webkit-justify-content: space-between;
      -moz-justify-content: space-between;
      -ms-justify-content: space-between;
      -o-justify-content: space-between;
      align-items: center;
      -webkit-align-items: center;
      -moz-align-items: center;
      -ms-align-items: center;
      -o-align-items: center;
    }
  }
}
</style>

