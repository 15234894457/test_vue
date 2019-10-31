<template>
  <div>
      <img src="../../assets/log.jpg" class="img" :style="contentStyleObj">
       <el-form :model="ruleForm2" :rules="rules2"
         status-icon
         ref="ruleForm2" 
         label-position="left" 
         label-width="0px" 
         class="demo-ruleForm login-page"
         style="box-card">
            <h3 class="title">系统登录</h3>
            <el-form-item prop="username">
                <el-input type="text" 
                    v-model="ruleForm2.username" 
                    auto-complete="off" 
                    placeholder="用户名"
                ></el-input>
            </el-form-item>
                <el-form-item prop="password">
                    <el-input type="password" 
                        v-model="ruleForm2.password" 
                        auto-complete="off" 
                        placeholder="密码"
                    ></el-input>
                </el-form-item>
            <el-checkbox 
                v-model="checked"
                class="rememberme"
            >记住密码</el-checkbox>
            <el-form-item style="width:100%;">
                <el-button type="primary" style="width:100%;" @click="handleSubmit" :loading="logining">登录</el-button>
            </el-form-item>
        </el-form>
  </div>
</template>
<style>
.login-page {
    -webkit-border-radius: 5px;
    border-radius: 5px;
    width: 340px;
    background: rgba(200,200,200,0.6);
    padding: 35px 35px 15px;
    position: absolute;
    top:35%;
    right: 300px;   
}
label.el-checkbox.rememberme {
    margin: 0px 0px 15px;
    text-align: left;
}
  .img {
    display: block;
    width: 100%;
    height: 70%;
  }
  .text {
    font-size: 14px;
    text-align: center;
  }
  .box-card {
    position: fixed;
    top: 345px;
    left: 68%;
    width: 381px;
    height: 280px;
    background: rgba(255,255,255,0.5);
  }
</style>
<script>
export default {
  data () {
    return {
       contentStyleObj:{
　　　　　　height:''
　　　　},
     logining: false,
            ruleForm2: {
                username: '',
                password: '',
            },
            rules2: {
                username: [{required: true, message: 'please enter your account', trigger: 'blur'}],
                password: [{required: true, message: 'enter your password', trigger: 'blur'}]
            },
            checked: false
        }

  },
  created(){
    window.addEventListener('resize', this.getHeight);
    this.getHeight()
    console.log(this.getHeight())
  },
  destroyed(){
    window.removeEventListener('resize', this.getHeight)
  },
  methods: {
    getHeight(){
      this.contentStyleObj.height=window.innerHeight+'px';
    },
    handleSubmit() {
      this.$message('这是一条消息提示username:'+this.userName+'这是一条消息提示password:'+this.passWord);
      this.$router.push({name:'home'})
    }
  }
}
</script>
