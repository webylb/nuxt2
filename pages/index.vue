<template>
  <section class="home wrap">
    <platformHeader/>
    <div class="home-banner relative">
      <el-button class="apply-add absolute" @click="applyAdd">申请加入</el-button>
    </div>
    <div class="container">
      <h2 class="section-title">市场前景</h2>
      <p class="section-text">船帆已启航，只需与你共掌舵</p>
      <div class="market-content">
        <div class="mc-descript relative">
          <img src="/image/mc-img.jpg" alt="市场前景" class="absolute mc-img">
          <h3 class="mc-title">百亿级市场，朝阳行业</h3>
          <ul class="mc-list">
            <li>团队服、活动服、校服、工服、文化衫等已经被越来越多的团队、企业和学校等重视。</li>
            <li>传统行业模式限制，使定制行业市场未出现优势品牌。</li>
            <li>定制B2B，B2C模式，在短时间内迅速崛起。4年时间已超过传统行业数十年的积累和口碑。</li>
          </ul>
        </div>
      </div>
    </div>
    <h2 class="section-title">实例规模</h2>
    <p class="section-text">4年运营沉淀，只待与君携手共进</p>
    <div class="scale-content">
      <div class="sc-left">
        <div>
          <img src="" alt="">
        </div>
      </div>
      <div class="sc-center">
        <div>
          <img src="" alt="">
        </div>
      </div>
      <div class="sc-right">
        <div>
          <img src="" alt="">
        </div>
      </div>
    </div>
    <div class="testdiv">
      <logo/>
    </div>
    <div class="form-jump">
      666;



      qqweqwe

    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import platformHeader from '~/components/platformHeader'

export default {
  name: 'Home',
  components: {
    Logo,
    platformHeader
  },
  methods: {
    applyAdd(){
      //console.log("666");
      // 用 class="form-jump" 添加锚点
      let jump = document.querySelector('.form-jump');
      let total = jump.offsetTop;
      let distance = document.documentElement.scrollTop || document.body.scrollTop;
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
.home {
  text-align: center;
  .home-banner {
    width: 100%;
    height: calc(100vh - 70px);
    background: #fff url("/image/home-banner.jpg") no-repeat center;
    background-size: cover;
    .apply-add {
      bottom: 50px;
      left: 50%;
      transform: translateX(-50%);
      width: 385px;
      height: 52px;
      padding: 0;
      line-height: 52px;
      border-radius: 8px;
      border-top-right-radius: 0;
      border-bottom-left-radius: 0;
      color: #fff;
      border: none;
      background: -webkit-linear-gradient(#fbf348, #938d1d); /* Safari 5.1 - 6.0 */
      background: -o-linear-gradient(#fbf348, #938d1d); /* Opera 11.1 - 12.0 */
      background: -moz-linear-gradient(#fbf348, #938d1d); /* Firefox 3.6 - 15 */
      background: linear-gradient(#fbf348, #938d1d);
      -moz-box-shadow: -3px 3px 3px #6f6c0d; /* 老的 Firefox */
      box-shadow: -3px 3px 3px #6f6c0d;
      font-size: 18px;
      font-weight: bold;
      letter-spacing: 4px;
    }
  }
  .section-title {
    font-size: 30px;
    font-weight: 600;
    margin-top: 60px;
  }
  .section-text {
    font-size: 30px;
    margin-top: 20px;
    margin-bottom: 60px;
  }
  .market-content {
    display: -webkit-box;
    display: -webkit-flex;
    display: -ms-flexbox;
    display: flex;
    justify-content: flex-end;
    -webkit-justify-content: flex-end;
    -moz-justify-content: flex-end;
    -ms-justify-content: flex-end;
    -o-justify-content: flex-end;
    padding-bottom: 50px;
    .mc-descript {
      padding: 50px;
      border: 2px solid #333;
      margin-right: 100px;
      .mc-img {
        left: -600px;
        top: 50%;
        width: 630px;
        height: auto;
        transform: translateY(-50%);
      }
      .mc-title {
        font-size: 30px;
        font-weight: 600;
        margin-bottom: 50px;
      }
      .mc-list {
        text-align: left;
        list-style: disc;
        width: 200px;
        display: inline-table;
        font-size: 16px;
        li {
          list-style: disc;
          margin-bottom: 50px;
          line-height: 30px;
          &:last-child {
            margin-bottom: 0;
          }
        }
      }
    }
  }
  .scale-content {
    display: -webkit-box;
    display: -webkit-flex;
    display: -ms-flexbox;
    display: flex;
    justify-content: space-around;
    -webkit-justify-content: space-around;
    -moz-justify-content: space-around;
    -ms-justify-content: space-around;
    -o-justify-content: space-around;
    padding-bottom: 50px;
  }
}
</style>
