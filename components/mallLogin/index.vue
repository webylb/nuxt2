<template>
  <section class="mallLogin-wrap">
    <div class="mallLogin">
      <div class="close">
        <el-button type="text" icon="el-icon-circle-close-outline" @click="closeLogin" />
      </div>
      <div class="register-form">
        <h2 class="form-title">登录</h2>
        <el-form ref="ruleForm" :model="ruleForm" :rules="rules" status-icon class="demo-ruleForm">
          <el-form-item prop="phone">
            <el-input v-model.number="ruleForm.phone" autocomplete="off" prefix-icon="el-icon-mobile-phone" placeholder="请输入手机号码" />
          </el-form-item>
          <el-form-item prop="pass">
            <el-input v-model="ruleForm.pass" type="password" autocomplete="off" prefix-icon="el-icon-mobile-phone" placeholder="请输入密码"/>
          </el-form-item>
          <el-form-item class="rem-word" prop="remember">
            <el-checkbox-group v-model="ruleForm.remember">
              <el-checkbox label="记住密码" name="remember" />
              <el-button type="text" class="fw-link" @click="goFgtword">忘记密码?</el-button>
            </el-checkbox-group>
          </el-form-item>
          <el-form-item>
            <el-button class="subRegisterForm" @click="submitForm('ruleForm')">登录</el-button>
          </el-form-item>
          <el-form-item>
            <div class="registerForm-bottom">
              还没有账号?
              <nuxt-link to="/register" class="bc-link">
                去注册
              </nuxt-link>
            </div>
          </el-form-item>
        </el-form>
      </div>
    </div>
  </section>
</template>

<script>
import { mapState, mapActions, mapMutations } from 'vuex'

export default {
  name: "MallLogin",
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
        remember: true
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
      }
    };
  },
  computed: {
    ...mapState(['isShowLogin'])
  },
  methods: {
    ...mapMutations(['CHANGE_ISSHOWLOGIN']),
    closeLogin(){
      this.CHANGE_ISSHOWLOGIN(false)
    },
    goFgtword() {
      this.push("/");
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

<style>
  .mallLogin .el-checkbox__input.is-checked+.el-checkbox__label {
    color: #333;
  }
</style>
<style lang="less" scoped>
//定义变量
@color : #FA6600;
@hoverColor: rgb(190,63,0);

.mallLogin-wrap {
  position: fixed;
  left: 0;
  top: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0,0,0,0.3);
  z-index: 99;
  .mallLogin {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    -webkit-transform: translate(-50%,-50%);
    -moz-transform: translate(-50%,-50%);
    -ms-transform: translate(-50%,-50%);
    -o-transform: translate(-50%,-50%);
    background-color: #fff;
    width: 450px;
    -moz-box-shadow:0px 0px 3px #d4bbbb;
    -webkit-box-shadow:0px 0px 3px #d4bbbb;
    box-shadow:0px 0px 3px #d4bbbb;
    border-radius: 5px;
    .close {
      height: 40px;
      text-align: right;
      .el-button {
        font-size: 18px;
        padding: 10px;
      }
    }
    .register-form {
      padding: 0px 45px;
      .form-title {
        text-align: center;
        margin-bottom: 25px;
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
      .rem-word {
        margin-bottom: 16px;
        .fw-link {
          float: right;
        }
      }
      .registerForm-bottom {
        display: -webkit-box;
        display: -webkit-flex;
        display: -ms-flexbox;
        display: flex;
        justify-content: center;
        -webkit-justify-content: center;
        -moz-justify-content: center;
        -ms-justify-content: center;
        -o-justify-content: center;
        line-height: 30px;
        .bc-link {
          color:#333;
          margin-left: 10px;
          // font-size: 16px;
        }
      }
    }
  }
}
</style>
