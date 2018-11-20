<template>
  <section class="home wrap">
    <platformHeader/>
    <div class="home-banner relative">
      <el-button class="apply-add absolute" @click="applyAdd">申请加入</el-button>
    </div>
    <div class="container">
      <!-- section1 -->
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
      <!-- section2 -->
      <h2 class="section-title">实例规模</h2>
      <p class="section-text">4年运营沉淀，只待与君携手共进</p>
      <div class="scale-content">
        <div class="sc-left">
          <div class="relative">
            <img src="/image/sc-left.jpg" alt="Makers">
            <div class="absolute sc-border-wrap"/>
          </div>
          <div class="sc-text">
            <h4>合作产商</h4>
            <p>400+顶级供应商</p>
          </div>
        </div>
        <div class="sc-center">
          <div class="sc-text">
            <h4>加工厂</h4>
            <p>10+遍布珠三角</p>
          </div>
          <div class="relative">
            <img src="/image/sc-center.jpg" alt="factory">
            <div class="absolute sc-border-wrap"/>
          </div>
        </div>
        <div class="sc-right">
          <div class="sc-img-warp relative">
            <img src="/image/sc-right1.png" alt="Alibaba">
            <img src="/image/sc-right2.png" alt="PING AN">
            <img src="/image/sc-right3.png" alt="XIAO MI">
            <div class="absolute sc-border-wrap"/>
          </div>
          <div class="sc-text">
            <h4>合作伙伴</h4>
            <p>1000+全国各地</p>
          </div>
        </div>
      </div>
      <p class="scale-text">
        四年定制行业运营经验,行业数据化和品牌化的倡导者和引领者。阿里巴巴2014年纽约PO的13万件文化衫就是我们公司及时响应生产,花费7天,派放到全球13万人的手中。赢得了阿里巴巴CEO马云的称赞。我们的客户超过3000家知名企业与教育机构,是各大重大赛事、活动定制品类的主要供应商。2018年全国战略布局建立2000+合伙人体系及线下店铺,打造定制行业的标杆。
      </p>
      <!-- section3 -->
      <h2 class="section-title">技术优势</h2>
      <p class="section-text">潜心钻研，只争朝夕</p>
      <div class="technology-content">
        <div class="tc-descript">
          <img src="/image/tc-img.png" alt="技术优势" class="tc-img">
        </div>
      </div>
      <!-- section4 -->
      <h2 class="section-title">客户案例</h2>
      <div class="client-content">
        <div class="cc-descript">
          <img src="/image/cc-img.jpg" alt="客户案例" class="cc-img">
        </div>
      </div>
      <!-- section5 -->
      <h2 class="section-title apply-title"><span>申请流程</span></h2>
      <div class="client-content">
        <!-- step1 -->
        <div class="cc-step">
          <div class="cc-step1 absolute">
            <span class="step-num">1</span><span class="step-title">提交申请</span><span class="step-text">填写基本信息</span>
          </div>
        </div>
        <!-- step2 -->
        <div class="cc-step">
          <div class="cc-step1 absolute">
            <span class="step-num">2</span><span class="step-title">线上沟通</span><span class="step-text">客服与你初步沟通</span>
          </div>
        </div>
        <!-- step3 -->
        <div class="cc-step">
          <div class="cc-step1 absolute">
            <span class="step-num">3</span><span class="step-title">审核沟通</span><span class="step-text">高层领导和你意向沟通</span>
          </div>
        </div>
        <!-- step4 -->
        <div class="cc-step">
          <div class="cc-step1 absolute">
            <span class="step-num">4</span><span class="step-title">签订协议</span><span class="step-text">签订正式授权协议</span>
          </div>
        </div>
        <!-- step5 -->
        <div class="cc-step">
          <div class="cc-step1 absolute">
            <span class="step-num">5</span><span class="step-title">实战指导</span><span class="step-text">运营大牛一对一辅导</span>
          </div>
        </div>
      </div>
      <!-- section6 -->
      <h2 class="section-title">申请加入</h2>
      <div class="applyAdd-content">
        <el-form ref="ruleForm" :model="ruleForm" :rules="rules" class="ruleForm">
          <el-form-item prop="sex">
            <el-radio-group v-model="ruleForm.sex">
              <el-radio label="男士" />
              <el-radio label="女士" />
            </el-radio-group>
          </el-form-item>
          <el-form-item label="您的姓名" prop="name" label-width="100px">
            <el-input v-model="ruleForm.name" type="text" placeholder="请输入您的名字"/>
          </el-form-item>
          <el-form-item label="您的电话" prop="phone" label-width="100px" >
            <el-input v-model.number="ruleForm.phone" placeholder="请输入您的联系方式"/>
          </el-form-item>
          <el-form-item label="所在区域" prop="city" label-width="100px">
            <area-cascader v-model="ruleForm.city" :data="pcaa" :level="1" type="all" placeholder="请选择地区"/>
          </el-form-item>
          <el-form-item>
            <el-button class="subApplyAdd" @click="submitForm('ruleForm')">提交</el-button>
          </el-form-item>
        </el-form>
      </div>
      <!-- section7 -->
      <h2 class="section-title form-jump">
        成为XXX的合作伙伴 <br>
        抢占市场先机,赚钱人生的第一桶金 <br>
        欢迎您加入至趣定制系统,共享百亿级定制市场
      </h2>
    </div>
    <div class="foot-content">
      <div class="foot-color-wrap" />
      <div class="">
        <img src="/image/home-foot-bg.jpg" alt="合作伙伴" class="foot-img">
      </div>
    </div>
  </section>
</template>

<script>
import platformHeader from '~/components/platformHeader'
import { pca, pcaa } from 'area-data'; // 城市数据
import 'vue-area-linkage/dist/index.css'; // 样式

export default {
  name: 'Home',
  components: {
    platformHeader
  },
  data() {
    let validatePhone = (rule, value, callback) => {
      let reg = /^1[34578]\d{9}$/
      if(!reg.test(value)){
        callback(new Error('手机号格式错误'))
      }else{
          callback()
      }
    };
    return {
      pca: pca,
      pcaa: pcaa,
      ruleForm: {
        name: '',
        phone: '',
        sex:'',
        city: ''
      },
      rules: {
        name: [
          { required: true, message: '请输入您的名字', trigger: 'blur' },
          { min: 3, max: 18, message: '长度在 3 到 18 个字符', trigger: 'blur' }
        ],
        phone: [
          { required: true, type: 'number', message: '请输入手机号码'},
          { validator:validatePhone, trigger: 'blur' }
        ],
        sex: [
          { required: true, message: '请选择性别', trigger: 'change' }
        ],
        city: [
          { required: true, message: '请填写活动形式', trigger: 'blur' }
        ]
      }
    };
  },
  methods: {
    applyAdd(){
      // 用 class="form-jump" 添加锚点
      let jump = document.querySelector('.form-jump');
      let total = jump.offsetTop + 400 ;
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
    },
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert('submit!');
        } else {
          console.log('error submit!!');
          return false;
        }
      });
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    }
  }

}
</script>

<style lang="less" scoped>
//定义变量
@color : #FA6600;
@hoverColor: rgb(190,63,0);

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
      -webkit-transform: translateX(-50%);
      -moz-transform: translateX(-50%);
      -ms-transform: translateX(-50%);
      -o-transform: translateX(-50%);
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
      -moz-box-shadow: -3px 3px 3px #6f6c0d;
      -webkit-box-shadow: -3px 3px 3px #6f6c0d;
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
        -webkit-transform: translateY(-50%);
        -moz-transform: translateY(-50%);
        -ms-transform: translateY(-50%);
        -o-transform: translateY(-50%);
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
    .sc-left {
      .relative {
        margin-bottom: 5%;
        .sc-border-wrap {
          width: 100%;
          height: 110%;
          left: 20px;
          top: -5%;
          border: 1px solid @color;
          z-index: -1;
        }
        img {
          width: 100%;
          height: auto;
        }
      }
    }
    .sc-center {
      .relative {
        margin-top: 5%;
        .sc-border-wrap {
          width: 100%;
          height: 110%;
          left: -20px;
          top: -5%;
          border: 1px solid @color;
          z-index: -1;
        }
        img {
          width: 100%;
          height: auto;
        }
      }
    }
    .sc-right {
      .sc-img-warp {
        margin-bottom: 5%;
        background-color: #fff;
        padding-left: 20px;
        width: 296px;
        height: 296px;
        img {
          display: block;
          margin: 0 auto;
          margin-bottom: 40px;
        }
        img:last-child {
          margin-bottom: 0;
        }
        .sc-border-wrap {
          width: 100%;
          height: 110%;
          left: 20px;
          top: -5%;
          border: 1px solid @color;
          z-index: -1;
        }
      }
    }
    .sc-text {
      padding: 15px 0;
      h4 {
        font-size: 24px;
      }
      p {
        font-size: 20px;
      }
    }

  }
  .scale-text {
    font-size: 20px;
    padding: 30px;
    line-height: 35px;
    letter-spacing: 3px;
    font-weight: 500;
    text-align: left;
    text-indent: 48px;
  }
  .technology-content {
    padding-bottom: 50px;
  }
  .apply-title {
    span {
      position: relative;
      &::before {
        content: "";
        height: 1px;
        width: 270px;
        border-top: 2px solid #000;
        position: absolute;
        left: -275px;
        top: 50%;
        transform: translateY(-50%);
        -webkit-transform: translateY(-50%);
        -moz-transform: translateY(-50%);
        -ms-transform: translateY(-50%);
        -o-transform: translateY(-50%);
      }
      &::after {
        content: "";
        height: 1px;
        width: 270px;
        border-top: 2px solid #000;
        position: absolute;
        right: -275px;
        top: 50%;
        transform: translateY(-50%);
        -webkit-transform: translateY(-50%);
        -moz-transform: translateY(-50%);
        -ms-transform: translateY(-50%);
        -o-transform: translateY(-50%);
      }
    }
  }
  .client-content {
    padding-bottom: 50px;
    text-align: left;
    .cc-step {
      position: relative;
      padding: 70px 0 70px 50px;
      .cc-step1 {
        left: 50%;
        width: 520px;
        transform: translateX(-40%);
        -webkit-transform: translateX(-40%);
        -moz-transform: translateX(-40%);
        -ms-transform: translateX(-40%);
        -o-transform: translateX(-40%);
        &::before {
          content: "";
          position: absolute;
          border-left: 1px dashed #000;
          height: 140px;
          left: 35px;
          top: -70px;
          z-index: -1;
        }
        .step-num {
          background-color: #333;
          color: #fff;
          border-radius: 50%;
          height: 70px;
          width: 70px;
          display: inline-block;
          text-align: center;
          font-size: 30px;
          line-height: 66px;
        }
        .step-title {
          font-size: 18px;
          padding:0 10px 0 15px;
          position: relative;
          &::after {
            content: "";
            width: 4px;
            height: 4px;
            background-color: #000;
            border-radius: 50%;
            position: absolute;
            right: -2px;
            top: 50%;
            transform: translateY(-40%);
            -webkit-transform: translateY(-40%);
            -moz-transform: translateY(-40%);
            -ms-transform: translateY(-40%);
            -o-transform: translateY(-40%);
          }
        }
        .step-text {
          font-size: 16px;
          padding: 0 0px 0 10px;
        }
      }
    }
  }
  .applyAdd-content {
    padding-bottom: 50px;
    margin-top: 35px;
    .ruleForm {
      width: 800px;
      margin: 0 auto;
      padding: 15px 75px 50px 75px;
      -moz-box-shadow:0px 0px 3px #000000;
      -webkit-box-shadow:0px 0px 3px #000000;
      box-shadow:0px 0px 3px #000000;
      border-radius: 4px;
      .subApplyAdd {
        background-color: @color;
        color: #fff;
        width: 225px;
        font-size: 16px;
        &:hover {
          background-color: @hoverColor;
        }
      }
    }
  }
  .foot-content {
    .foot-color-wrap {
      height: 70px;
      background: -webkit-linear-gradient(#fff,#f9f9f9);
      background: -o-linear-gradient(#fff,#f9f9f9);
      background: -moz-linear-gradient(#fff,#f9f9f9);
      background: -mos-linear-gradient(#fff,#f9f9f9);
      background: linear-gradient(#fff,#f9f9f9);
    }
    img {
      width: 100%;
      height: auto;
    }
  }
}
</style>
