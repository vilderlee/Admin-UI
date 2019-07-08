<template>
  <div class="login-container">
    <el-form ref="form" :model="form" label-position="right">
      <div class="title-container">
        <h3 class="title">Login Form</h3>

        <div class="i18-container">
          <el-dropdown trigger="click" @command="changeLangEvent">
            <i class="iconfont icon-en"></i>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item command="CN">中</el-dropdown-item>
              <el-dropdown-item command="EN">EN</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </div>
      </div>
      <el-form-item class="input-container">
        <div class="svg-container">
          <i class="iconfont icon-Personal"></i>
        </div>
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item class="input-container">
        <div class="svg-container">
          <i class="iconfont icon-Password"></i>
        </div>
        <el-input v-model="form.password" placeholder="请输入密码" show-password></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit()">{{$t('lang.login')}}</el-button>
        <el-button>注册</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {}
    };
  },

  methods: {
    onSubmit() {},

    changeLangEvent(command) {
      console.info(this.$i18n.locale);
      if(command == 'CN'){
          this.$i18n.locale = "zh-CN";
      }else if(command == 'EN'){
          this.$i18n.locale = "en-US";
      }
    //   if (this.$i18n.locale === "zh-CN") {
    //     this.$i18n.locale = "en-US"; //关键语句
    //     console.log("en-US");
    //   } else {
    //     this.$i18n.locale = "zh-CN"; //关键语句
    //     console.log("zh-CN");
    //   }
    }
  }
};
</script>

<style rel="stylesheet/scss" lang="scss">
@import "../iconfont/iconfont.css";
.iconfont {
  font-size: 21px;
  color: rgb(194, 192, 192);
}
.login-container {
  top: 0px;
  left: 0px;
  width: 100%;
  min-height: 100%;
  height: 100%;
  background-color: #2d3a4b;
  overflow: hidden;
  margin: 0px;
  position: fixed;

  .el-form {
    position: relative;
    width: 520px;
    max-width: 100%;
    padding: 200px 35px 0;
    margin: 0 auto;
    overflow: hidden;
  }
  .input-container {
    border: 1px solid rgba(255, 255, 255, 0.1);
    background: rgba(0, 0, 0, 0.1);
    border-radius: 5px;
    color: #454545;
    width: 500px;
    margin-top: 10px;
    padding: 3px, 50px, 3px, 50px;

    .svg-container {
      padding-top: 8px;
      padding-bottom: 0px;
      margin-left: 0px;
      display: inline-block;
    }

    .el-input {
      display: inline-block;
      height: 47px;
      width: 85%;
      input {
        color: #fff;
        background: transparent;
        border: #2d3a4b;
        height: 40px;
      }
    }
  }
  .title-container {
    width: 500px;

    .title {
      font-size: 26px;
      color: #fff;
      margin: 0px auto 40px auto;
      text-align: center;
      font-weight: bold;
    }
  }
}
</style>
