<template>
  <section class="mallProduct wrap">
    <mallHeader/>
    <div class="container">
      <el-breadcrumb separator-class="el-icon-arrow-right" class="productBreadcrumb">
        <el-breadcrumb-item v-for="(item,index) in productBreadcrumb" :key="index" :to="{ path: item.link }">{{ item.name }}</el-breadcrumb-item>
      </el-breadcrumb>
      <div class="product-detail">
        <el-row :gutter="10">
          <el-col :xs="14" :sm="14" :md="14" :lg="14" :xl="14">
            <div class="productList-bigImg">
              <div v-for="(item,index) in imgList" v-show="index == active ? true : false" :key="index" class="productList-bigItem">
                <img :src="item.img" :alt="item.alt" :index="index">
              </div>
            </div>
            <div class="productList-thumb">
              <div v-for="(item,index) in thumbList" :key="index" class="productList-thumbItem" @click="changeActive(index)">
                <img :src="item.img" :alt="item.alt">
              </div>
            </div>
          </el-col>
          <el-col :xs="10" :sm="10" :md="10" :lg="10" :xl="10">
            <h1>男士V领纯棉T恤</h1>
            <p class="des-p">
              {{ descript }}
            </p>
            <div class="color-choose desItem">
              <div class="desItem-title">颜色:</div>
              <ul class="color-list">
                <li v-for="(item,index) in colorList" :key="index" class="color-item">
                  <img :src="item.img" :alt="item.alt">
                </li>
              </ul>
            </div>
            <div class="size-choose desItem">
              <div class="desItem-title">规格:</div>
              <ul class="size-list">
                <li v-for="(item,index) in colorList" :key="index" class="size-item">
                  <img :src="item.img" :alt="item.alt">
                </li>
              </ul>
            </div>
            <div class="price desItem">
              <div class="desItem-title">价格:</div>
              <div v-if="isLogin" class="price-item">$220</div>
              <div v-else class="price-item">登陆查价</div>
            </div>
            <el-button class="start-c desItem" @click="showInquire">开始定制</el-button>
          </el-col>
        </el-row>
      </div>
      <div class="product-descript">
        <!-- section1 -->
        <section class="des-imgList">
          <div v-for="(item,index) in desImgList" :key="index" class="des-imgItem">
            <img :src="item.img" :alt="item.alt">
          </div>
        </section>
        <!-- section2 -->
        <section class="des-imgList">
          <h2 class="des-sectionTitle">
            <p class="samllText">CUSTOM TECHNOLOGY</p>
            <p class="bigText">定制技术</p>
          </h2>
          <div class="des-imgItem sizeImg">
            <img :src="techImg.img" :alt="techImg.alt">
          </div>
        </section>
        <!-- section3 -->
        <section class="des-imgList design-section">
          <h2 class="des-sectionTitle">
            <p class="samllText">DESIGN SPECIFICATION</p>
            <p class="bigText">设计规格</p>
          </h2>
          <div class="des-imgItem sizeImg">
            <img :src="designImg.img" :alt="designImg.alt">
          </div>
          <p class="size-hint"><em> · 前胸/后背定制尺寸范围: 28cmX35cm</em></p>
        </section>
        <!-- section4 -->
        <section class="des-imgList attr-section">
          <h2 class="des-sectionTitle">
            <p class="samllText">PRODUCT ATTRIBUTES</p>
            <p class="bigText">产品属性</p>
          </h2>
          <div class="des-imgItem sizeImg">
            <img :src="pArrtImg.img" :alt="pArrtImg.alt">
          </div>
          <p class="size-hint"> · 因灯光显示屏等原因,商品图片与实物颜色可能略有偏差,请以实物为准!</p>
        </section>
        <!-- section5 -->
        <section class="des-imgList">
          <h2 class="des-sectionTitle">
            <p class="samllText">PRODUCT SIZE TABLE</p>
            <p class="bigText">产品尺码表</p>
          </h2>
          <div class="des-imgItem sizeImg">
            <img :src="size.img" :alt="size.alt">
          </div>
          <p class="size-hint"> · 因平铺测量方式差异,可能有细微误差,敬请谅解!</p>
        </section>
        <!-- section6 -->
        <section class="des-imgList">
          <h2 class="des-sectionTitle">
            <p class="samllText">PRODUCT DESCRIPTION</p>
            <p class="bigText">产品展示</p>
          </h2>
          <div class="des-imgItem sizeImg">
            <img :src="desImg.img" :alt="desImg.alt">
          </div>
        </section>
      </div>
    </div>
    <inquire v-show="isShowInquire" />
    <mallFooter/>
  </section>
</template>

<script>
import mallHeader from '~/components/mallHeader'
import { mapState, mapActions, mapMutations } from 'vuex'

export default {
  name: "Mall",
  components: {
    mallHeader,
    mallFooter: () => import('@/components/mallFooter'),
    inquire: () => import('@/components/inquire'),
  },
  data(){
    return {
      productBreadcrumb: [
        {name:'全部产品',link:"/mall/category"},
        {name:"扩展产品",link:"/mall/category"},
        {name:"T恤",link:"/mall/category"}
      ],
      thumbList: [
        {img:"/image/thumb-product.png", alt:"男士V领纯棉T恤"},
        {img:"/image/thumb-product.png", alt:"男士V领纯棉T恤"},
        {img:"/image/thumb-product.png", alt:"男士V领纯棉T恤"},
        {img:"/image/thumb-product.png", alt:"男士V领纯棉T恤"}
      ],
      imgList: [
        {img:"/image/big-product.png", alt:"男士V领纯棉T恤"},
        {img:"/image/big-product.png", alt:"男士V领纯棉T恤"},
        {img:"/image/big-product.png", alt:"男士V领纯棉T恤"},
        {img:"/image/big-product.png", alt:"男士V领纯棉T恤"}
      ],
      active: 0,
      descript: "男士V领纯棉T恤男士V领纯棉T恤男士V领纯棉T恤男士V领纯棉T恤男士V领纯棉T恤男士V领纯棉T恤",
      isLogin: false,
      colorList: [
        {img:"/image/thumb-product.png", alt:"黑色"},
        {img:"/image/thumb-product.png", alt:"黑色"},
        {img:"/image/thumb-product.png", alt:"黑色"},
        {img:"/image/thumb-product.png", alt:"黑色"}
      ],
      desImgList: [
        {img:'/image/product-des1.jpg', alt:"desIMG"},
        {img:'/image/product-des2.jpg', alt:"desIMG"},
        {img:'/image/product-des3.jpg', alt:"desIMG"},
        {img:'/image/product-des4.jpg', alt:"desIMG"},
        {img:'/image/product-des5.jpg', alt:"desIMG"}
      ],
      size:{ img:"/image/size.jpg", alt:"szie" },
      pArrtImg: {img:'/image/product-attr.jpg', alt:"desIMG"},
      designImg: {img:'/image/design-img.jpg', alt:"desIMG"},
      techImg: {img:'/image/tech.jpg', alt:"desIMG"},
      desImg: {img:'/image/des-img.jpg', alt:"desIMG"}

    };
  },
  computed: {
    ...mapState(['isShowInquire'])
  },
  methods: {
    ...mapMutations(['CHANGE_ISSHOWINQUIRE']),
    changeActive(param) {
      console.log(param);
      this.active = param;
    },
    showInquire(){
      console.log(this.$store.state.isShowInquire);
      this.CHANGE_ISSHOWINQUIRE(true)
    },
  }
}
</script>

<style lang="less" scoped>
//定义变量
@color : #FA6600;
@hoverColor: rgb(190,63,0);

.mallProduct {
  .productBreadcrumb {
    height: 45px;
    line-height: 45px;
    background-color: #ebebeb;
    padding: 0 10px;
    border-radius: 4px;
    margin: 20px 0;
  }
  .productList-bigImg {
    margin: 0 auto;
    max-width: 566px;
    height: auto;
  }
  .productList-thumb {
    margin: 0 auto;
    margin-top: 20px;
    max-width: 566px;
    height: auto;
    display: -webkit-box;
    display: -webkit-flex;
    display: -ms-flexbox;
    display: flex;
    justify-content: space-between;
    -webkit-justify-content: space-between;
    -moz-justify-content: space-between;
    -ms-justify-content: space-between;
    -o-justify-content: space-between;
    .productList-thumbItem {
      cursor: pointer;
    }
  }
  h1 {
    margin-top: 20px;
    font-size: 26px;
  }
  .des-p {
    margin: 25px 0 40px 0;
  }
  .desItem {
    margin-bottom: 40px;
    font-size: 18px;
    display: -webkit-box;
    display: -webkit-flex;
    display: -ms-flexbox;
    display: flex;
    justify-content: flex-start;
    -webkit-justify-content: flex-start;
    -moz-justify-content:  flex-start;
    -ms-justify-content: flex-start;
    -o-justify-content:  flex-start;
    flex-wrap: wrap;
  }
  .color-list,.size-list,.price-item{
    flex: 1;
    margin-left: 20px;
    .color-item,.size-item,{
      display: inline-block;
      width: 30px;
      height: 30px;
      margin: 0 5px;
      img {
        width: 30px;
        height: 30px;
      }
    }
  }
  .start-c {
    background-color: @color;
    color: #fff;
    &:hover {
      background-color: @hoverColor;
    }
  }
  .product-descript {
    border-top: 1px dashed #c9c9c9;
    margin-top: 45px;
    padding: 35px 0;
    .des-imgList {
      width: 790px;
      margin: 0 auto;
      display: -webkit-box;
      display: -webkit-flex;
      display: -ms-flexbox;
      display: flex;
      justify-content: space-between;
      -webkit-justify-content: space-between;
      -moz-justify-content:   space-between;
      -ms-justify-content: space-between;
      -o-justify-content:  space-between;
      flex-wrap: wrap;
      .des-imgItem {
        margin-bottom: 10px;
      }
    }
    .des-sectionTitle {
      text-align: center;
      margin: 50px auto;
      .samllText {
        font-size: 12px;
        border-bottom: 2px solid #000;
        font-weight: 500;
      }
      .bigText {
        line-height: 20px;
      }
    }
    .sizeImg {
      width: 100%;
      img {
        width: 100%;
        height: auto;
      }
    }
    .size-hint {
      border: 1px solid #ededed;
      width: 100%;
      padding: 5px 10px;
      color: #aaaaaa;
    }
    .attr-section {
      background-color: #f5f5f5;
      padding: 35px;
      .size-hint {
        border: none;
      }
    }
    .design-section {
      padding: 35px;
      .size-hint {
        border: none;
        letter-spacing: 2px;
        text-align: center;
      }
    }
  }
}
</style>

