<template>
  <el-row>
    <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
      <div class="register warp relative">
        <div class="back-home absolute">
          <nuxt-link to="/" class="register-back-link">
            <div class="back-icon el-icon-arrow-left" />
            <div>返回平台首页</div>
          </nuxt-link>
        </div>
        <div class="register-form absolute">
          <h2 class="form-title">注册</h2>
          <el-form ref="ruleForm" :model="ruleForm" :rules="rules" status-icon class="demo-ruleForm">
            <el-form-item prop="phone">
              <el-input v-model.number="ruleForm.phone" autocomplete="off" prefix-icon="el-icon-mobile-phone" placeholder="请输入手机号码" />
            </el-form-item>
            <el-form-item prop="pass">
              <el-input v-model="ruleForm.pass" type="password" autocomplete="off" prefix-icon="el-icon-mobile-phone" placeholder="请输入密码"/>
            </el-form-item>
            <el-form-item prop="Code">
              <el-col :span="15">
                <el-input v-model="ruleForm.Code" type="text" autocomplete="off" prefix-icon="el-icon-mobile-phone" placeholder="请输入验证码" />
              </el-col>
              <el-col v-if="isCode" :span="7" :offset="2">
                <el-button class="code-info" type="info">获取验证码</el-button>
              </el-col>
              <el-col v-else :span="7" :offset="2">
                <img :src="Code" class="code-img" alt="验证码">
              </el-col>
            </el-form-item>
            <el-form-item>
              <el-button class="subRegisterForm" @click="submitForm('ruleForm')">注册</el-button>
              <!-- <el-button @click="resetForm('ruleForm')">重置</el-button> -->
            </el-form-item>
            <el-form-item>
              <div class="registerForm-bottom">
                <nuxt-link to="/" class="fb-link">
                  注册即同意《GOODATALL用户注册协议》
                </nuxt-link>
                <el-button type="text">
                  <nuxt-link to="/login" class="bc-link">
                    登录
                  </nuxt-link>
                </el-button>
              </div>
            </el-form-item>
          </el-form>
        </div>
      </div>
    </el-col>
  </el-row>
</template>

<script>

export default {
  data() {
    let validatePhone = (rule, value, callback) => {
      let reg = /^1[34578]\d{9}$/
      if(!reg.test(value)){
        callback(new Error('手机号格式错误'))
      }else{
          callback()
      }
    };
    let validateCode = (rule, value, callback) => {
      if (value === '') {
      }
    }
    return {
      ruleForm: {
        phone: '',
        pass: '',
        Code: ''
      },
      rules: {
        phone: [
          { required: true, type: 'number', message: '请输入手机号码'},
          { validator:validatePhone, trigger: 'blur' }
        ],
        pass: [
          { required: true, message: '请输入密码',trigger: 'blur'},
          { min: 6, message: '密码长度最少为6位', trigger: 'blur' }
        ],
        Code: [
          {required: true, message: '请输入验证码'},
          { validator: validateCode, trigger: 'blur' }
        ]
      },
      isCode: true
    };
  },
  methods: {
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

.register {
  width: 100vw;
  height: 100vh;
  background: url("/image/register-bg.jpg") no-repeat center;
  object-fit: cover;
  background-size: cover;
  .back-home {
    left: 50px;
    top: 50px;
    .register-back-link {
      color: #fff;
      font-size: 20px;
      div {
        display: inline-block;
      }
      .back-icon {
        font-size: 20px;
        border-radius: 50%;
        border: 1px solid #fff;
        padding: 10px;
        margin-right: 10px;
      }
    }
  }
  .register-form {
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    -webkit-transform: translate(-50%,-50%);
    -moz-transform: translate(-50%,-50%);
    -ms-transform: translate(-50%,-50%);
    -o-transform: translate(-50%,-50%);
    background-color: #fff;
    padding: 40px 90px;
    width: 520px;
    .form-title {
      text-align: center;
      margin-bottom: 25px;
    }
    .code-info{
      padding: 12px 13px;
    }
    .code-img {
      width: 100%;
      height: 100%;
    }
    .subRegisterForm {
      width: 100%;
      background-color: @color;
      color: #fff;
      font-size: 18px;
      &:hover {
        background-color: @hoverColor;
      }
    }
    .registerForm-bottom {
      display: -webkit-box;
      display: -webkit-flex;
      display: -ms-flexbox;
      display: flex;
      justify-content: space-between;
      -webkit-justify-content: space-between;
      -moz-justify-content: space-between;
      -ms-justify-content: space-between;
      -o-justify-content: space-between;
      line-height: 30px;
      .fb-link {
        display: block;
        height: 100%;
        color:#333;
      }
      .el-button {
        font-size: 18px;
        padding: 0;
        .bc-link {
          color:#333;
        }
      }
    }
  }
}
</style>

