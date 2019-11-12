<template>
    <div>
        <div>
            <img class="pic" src="../../assets/half.png">
        </div>
        <div class="login_form">
            <el-input v-model="userName" placeholder="=账号=" style="width:80%" clearable></el-input>
            <br><br/>
            <el-input v-model="password" placeholder="=密码=" style="width:80%" clearable></el-input>
            <br><br/>
            <el-button type="primary" @click="login">登录</el-button>
            <el-button plain @click="register">注册</el-button>
            <br><br/>
            <span style="color: #A9A9AB" @click="forget">忘记密码？点我点我</span>
        </div>
    </div>
  <!-- <div class="bg">
    <div class="outer_label">
      <img class="inner_label login_logo" src="../../assets/login.jpg">
    </div>
    <div class="login_form">
      <el-input v-model="userName" placeholder="-用户名-" style="width:50%"></el-input>
      <br><br/>
      <el-input v-model="password" placeholder="-密码-" style="width:50%"></el-input>
      
      <br><br/>
      <el-button type="primary">主要按钮</el-button>
      <el-button round>圆形按钮</el-button>
      <div style="margin-top: 10px">
        <span style="color: #000099;" @click="login">司机账号登陆</span><span style="float: right;color: #A9A9AB">忘记密码？</span>
      </div>
    </div>
  </div> -->
</template>
 
<script>
//  import { userLogin } from '../../api/api';
 
  export default {
    data() {
      return {
        userName: '',
        password: '',
        isBtnLoading: false
      }
    },
    created () {
      if(JSON.parse( localStorage.getItem('user')) && JSON.parse( localStorage.getItem('user')).userName){
        this.userName = JSON.parse( localStorage.getItem('user')).userName;
        this.password = JSON.parse( localStorage.getItem('user')).password;
      }
    },
    computed: {
      btnText() {
        if (this.isBtnLoading) return '登录中...';
        return '登录';
      }
    },
    methods: {
      login() {
        if (!this.userName) {
          this.$message.error('请输入用户名');
          return;
        }
        if (!this.password) {
          this.$message.error('请输入密码');
          return;
        }
 
      },
      register(){
          this.$message.success('注册成功');
      },
      forget(){
           this.$message({
          message: '点我也没用',
          center: true
        });
      }
    }
  }
</script>
<style>
  .pic{
      width: 100%;
      height: 364px;
  }

  .bg{
    background: url("../../assets/cat.jpg");
    background-repeat: no-repeat;
    background-size: 100%;
    width: 375px;
    height: 728px;
  }
  .outer_label{
      background-size: cover;
    width: 500px;
    height: 364px;
  }
  .login_form {
    padding-top: 5%;
    padding-left: 10%;
    padding-right: 10%;
  }
  .qxs-ic_user {
    /* background: url("../../assets/login/ic_user.png") no-repeat; */
    background-size: 13px 15px;
    background-position: 3%;
  }
  .qxs-ic_password {
    /* background: url("../../assets/login/ic_password.png") no-repeat; */
    background-size: 13px 15px;
    background-position: 3%;
    margin-bottom: 20px;
  }
  .login_logo {
    height: 100%;
  }
  .login_btn {
    width: 100%;
    font-size: 16px;
    background: -webkit-linear-gradient(left, #000099, #2154FA); /* Safari 5.1 - 6.0 */
    background: -o-linear-gradient(right, #000099, #2154FA); /* Opera 11.1 - 12.0 */
    background: -moz-linear-gradient(right, #000099, #2154FA); /* Firefox 3.6 - 15 */
    background: linear-gradient(to right, #000099 , #2154FA); /* 标准的语法 */
    filter: brightness(1.4);
  }
</style>