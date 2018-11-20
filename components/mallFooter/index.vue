<template>
  <el-row>
    <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
      <div class="mall-footer warp">
        <div class="container">
          <section class="mall-footer-list">
            <div class="mall-footer-item">
              <img src="/image/foot1.png" alt="联系我们">
              <p>联系我们</p>
              <p>808208820</p>
            </div>
            <div class="mall-footer-item">
              <img src="/image/foot2.png" alt="关于我们">
              <p>关于我们</p>
              <p>www.goodatall.com</p>
            </div>
            <div class="mall-footer-item">
              <img src="/image/foot3.png" alt="关注我们">
              <p>关注我们</p>
              <p>扫描图上二维码</p>
            </div>
            <div class="mall-footer-item">
              <img src="/image/foot4.png" alt="加入我们">
              <p>加入我们</p>
              <p>www.goodatall.com</p>
            </div>
          </section>
        </div>
      </div>
    </el-col>
  </el-row>
</template>


<style lang="less" scoped>
.mall-footer {
    padding: 50px 0;
    background-color: #f5f5f5;
    -moz-box-shadow:0px 0px 10px #dcdcdc;
    -webkit-box-shadow:0px 0px 10px #dcdcdc;
    box-shadow:0px 0px 10px #dcdcdc;
    .mall-footer-list {
      display: -webkit-box;
      display: -webkit-flex;
      display: -ms-flexbox;
      display: flex;
      justify-content: space-between;
      -webkit-justify-content: space-between;
      -moz-justify-content: space-between;
      -ms-justify-content: space-between;
      -o-justify-content: space-between;
      // align-items: center;
      // -webkit-align-items: center;
      // -moz-align-items: center;
      // -ms-align-items: center;
      // -o-align-items: center;
      .mall-footer-item {
        text-align: center;
        p {
          font-size: 22px;
          margin: 10px 0;
        }
      }
    }
  }
</style>




