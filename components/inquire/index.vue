<template>
  <section class="mallInquire-wrap">
    <div class="mallLogin">
      <div class="register-form">
        <h2 class="form-title">保存</h2>
        <p class="form-des">填写以下个人信息,方便我们与您联系</p>
        <el-form ref="ruleForm" :model="ruleForm" :rules="rules" status-icon class="demo-ruleForm">
          <el-form-item label="产品名称:">
            <el-input v-model="ruleForm.pname" />
          </el-form-item>
          <el-form-item label="设计名称:">
            <el-input v-model="ruleForm.dname" />
          </el-form-item>
          <el-form-item label="创建人:">
            <el-input v-model="ruleForm.cname" />
          </el-form-item>
          <el-form-item label="客户:">
            <el-input v-model="ruleForm.lname" />
          </el-form-item>
          <!-- <el-form-item prop="phone">
            <el-input v-model.number="ruleForm.phone" autocomplete="off" prefix-icon="el-icon-mobile-phone" placeholder="请输入手机号码" />
          </el-form-item>
          <el-form-item prop="pass">
            <el-input v-model="ruleForm.pass" type="password" autocomplete="off" prefix-icon="el-icon-mobile-phone" placeholder="请输入密码"/>
          </el-form-item> -->
          <el-form-item class="Inquire-buttonGroup">
            <el-button class="subRegisterForm" @click="submitForm('ruleForm')">提交</el-button>
            <el-button class="rebRegisterForm" @click="closeInquire">取消</el-button>
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
        remember: true,
        pname: '',
        dname: '',
        cname: '',
        lname: ''
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
    ...mapState(['isShowInquire'])
  },
  methods: {
    ...mapMutations(['CHANGE_ISSHOWINQUIRE']),
    closeInquire(){
      this.CHANGE_ISSHOWINQUIRE(false)
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

.mallInquire-wrap {
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
    .register-form {
      padding: 0px 45px;
      margin: 30px 0;
      .form-title {
        text-align: center;
      }
      .form-des {
        text-align: center;
        margin-bottom: 25px;
      }
      .el-form-item {
        margin-bottom: 2px;
        &:nth-last-child(2) {
          margin-bottom: 10px;
        }
      }
      .Inquire-buttonGroup {
        display: -webkit-box;
        display: -webkit-flex;
        display: -ms-flexbox;
        display: flex;
        justify-content: space-around;
        -webkit-justify-content: space-around;
        -moz-justify-content: space-around;
        -ms-justify-content: space-around;
        -o-justify-content: space-around;
        .subRegisterForm {
          background-color: @color;
          color: #fff;
          font-size: 16px;
          padding: 10px 30px;
          &:hover {
            background-color: @hoverColor;
          }
        }
        .rebRegisterForm {
          font-size: 16px;
          padding: 10px 30px;
        }
      }

    }
  }
}
</style>
