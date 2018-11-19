<template>
  <section class="plant wrap">
    <platformHeader/>

    <!-- section1 -->
    <section class="plant-content-banner relative">
      <div class="pcb-text absolute">
        <h1>XXX定制供应链</h1>
        <h3>自有工厂 + 全掌控供应链体系</h3>
        <p>降低成本 生产高效 一键定制</p>
      </div>
    </section>
    <!-- section2 -->
    <section class="plant-content-des relative">
      <div class="pcd-text absolute">
        <h2>至趣定制简介</h2>
        <p>至趣定制系统建于2015年,专注于团体服装定制的供应链服务,立志通过互联网信息技术实现定制行业标准化和信息化,提高并优化定制行业的生产效率。X齐多家优质的供应商、物流商,为全国各地的销售商提供最优质的供应链服务,响应市场需求,实现订单数据化,降低订单成本。至趣定制系统目前合作的供应商超过10多家,合作销售商1000多家。我们的目标是要成为全国最大的服饰定制供应链综合服务平台,为全国的销售商提供一站式的团体服饰定制服务。</p>
      </div>
    </section>
    <!-- section3 -->
    <section class="plant-content-adress relative">
      <div class="pca-text absolute">
        <h2>工厂区域</h2>
        <p>定制工厂汇集在珠三角</p>
        <p>一键式响应市场需求</p>
        <p>为每一位客户提供优质的服务</p>
      </div>
    </section>
    <!-- section4 -->
    <section class="plant-content-plant relative">
      <div class="pcp-text absolute">
        <h2>工厂实景</h2>
        <p>至趣定制系统加工厂位于深圳，总面积4000m<sup>2</sup>，丝印合位600个，</p>
        <p>多台配套齐全的打印机和刺绣机器，另配套6000m<sup>2</sup>的仓储中心能随时</p>
        <p>满足旺季的订单需求,并保证品质。</p>
      </div>
    </section>
    <section class="plant-content-way">
      1
    </section>
  </section>
</template>

<script>
import platformHeader from '~/components/platformHeader'

export default {
  name: 'Plant',
  components: {
    platformHeader
  }
}
</script>

<style lang="less" scoped>
.plant {
  .plant-content-banner {
    background:url("/image/plant1.jpg") no-repeat center;
    background-size: auto;
    height: 600px;
    .pcb-text {
      left: 51%;
      top: 50%;
      transform: translate(-50%, -50%);
      -webkit-transform: translate(-50%,-50%);
      -moz-transform: translate(-50%,-50%);
      -ms-transform: translate(-50%,-50%);
      -o-transform: translate(-50%,-50%);
      text-align: center;
      h1 {
        color: #7f7f7f;
        font-size: 50px;
        text-shadow: -3px 3px 5px #7f7f7f;
        letter-spacing: 5px;
      }
      h3 {
        font-size: 30px;
        font-weight: 500;
        margin: 40px auto;
      }
      p {
        font-size: 24px;
      }
    }
  }
  .plant-content-des {
    background:url("/image/plant2.jpg") no-repeat center;
    background-size: auto;
    height: 900px;
    .pcd-text {
      left: 49%;
      top: 50%;
      transform: translate(-50%, -50%);
      -webkit-transform: translate(-50%,-50%);
      -moz-transform: translate(-50%,-50%);
      -ms-transform: translate(-50%,-50%);
      -o-transform: translate(-50%,-50%);
      text-align: center;
      width: 700px;
      background: rgba(255, 255, 255, 0.6);
      border-radius: 10px;
      font-size: 24px;
      padding: 50px;
      line-height: 40px;
      text-align: left;
      h2 {
        text-align: center;
        font-size: 30px;
        margin-bottom: 10px;
      }
    }
  }
  .plant-content-adress {
    background:url("/image/plant3.jpg") no-repeat center;
    background-size: auto;
    height: 821px;
    .pca-text {
      right: 0%;
      top: 22%;
      transform: translate(-50%, -50%);
      -webkit-transform: translate(-50%,-50%);
      -moz-transform: translate(-50%,-50%);
      -ms-transform: translate(-50%,-50%);
      -o-transform: translate(-50%,-50%);
      text-align: center;
      width: 545px;
      background: rgba(255, 255, 255, 0.6);
      border-radius: 10px;
      font-size: 24px;
      padding: 50px;
      line-height: 40px;
      h2 {
        font-size: 30px;
        margin-bottom: 10px;
      }
    }
  }
  .plant-content-plant {
    background:url("/image/plant4.jpg") no-repeat center;
    background-size: auto;
    height: 936px;
    .pcp-text {
      left: 50%;
      top: 20%;
      transform: translate(-50%, -50%);
      -webkit-transform: translate(-50%,-50%);
      -moz-transform: translate(-50%,-50%);
      -ms-transform: translate(-50%,-50%);
      -o-transform: translate(-50%,-50%);
      text-align: center;
      width: 980px;
      font-size: 24px;
      padding: 50px;
      line-height: 40px;
      letter-spacing: 4px;
      h2 {
        font-size: 30px;
        margin-bottom: 10px;
      }
    }
  }
  .plant-content-way {
    background:url("/image/plant5.jpg") no-repeat center;
    background-size: auto;
    height: 3630px;
  }
}

</style>



