<template>
  <div class="sliderFixed">
    <h1 class="title">点选弹出式（point-popup）</h1>
    <p class="desc">
      点击自有验证按钮，弹出验证码，与自有业务样式完美融合
    </p>
    <el-row class="demo">
      <el-col :xs="24" :sm="24" :md="13" :lg="13" :xl="13" class="demo-result">
        <h2 class="result-title">示例</h2>
        <form class="result_form">
          <input
            class="result_input"
            type="text"
            value="用户名"
            disabled="disabled"
          >
          <input
            class="result_input"
            type="password"
            value="123456"
            disabled="disabled"
          >
          <!-- @success="login"  -->
          <Verify
            ref="verify"
            :mode="'pop'"
            :captcha-type="'clickWord'"
            :img-size="{ width: '330px', height: '155px' }"
          />
          <!-- 组件 -->
          <button class="result_btn" @click.prevent="$refs.verify.show()">登录</button>
        </form>
      </el-col>
      <el-col :xs="24" :sm="24" :md="11" :lg="11" :xl="11" class="demo-code">
        <div class="code-header clearfix">
          <h2 class="code-title">代码 :</h2>
          <!-- <button class="code_copy">复制</button> -->
        </div>
        <div class="code-container">
          <i>&lt;</i>template<i>></i>
          <pre>  <i>&lt;</i>Verify
     @success<i>=</i>"success"          //验证成功的回调函数
     :mode<i>=</i>"'pop'"               //调用的模式
     :captchaType="'clickWord'"    // //调用的类型 点选或者滑动
     :imgSize<i>=</i>"{ width: '330px', height: '155px' }" //图片的大小
     ref<i>=</i>"verify"
  <i>></i><i>&lt;</i>/Verify
<i>&lt;</i>/template<i>></i>

<i>&lt;</i>script<i>></i>
    //引入组件
    import Verify from "./../../components/verifition/Verify";

    export default {
        name: 'app',
        methods: {
          success(params){
            // params 返回的二次验证参数
          },
          showVerify(){
            //当mode="pop"时,调用组件实例的show方法显示组件
            this.$refs.verify.show();
          }
        },
        components<i>:</i> {
            Verify
        }
    }
<i>&lt;</i>/script<i>></i>
</pre>

        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import Verify from './../../components/verifition/Verify'

export default {
  name: 'SliderFixed',
  components: {
    Verify
  }
}
</script>

<style scoped lang="less">
.sliderFixed {
  .title {
    font-size: 28px;
    color: #222;
    line-height: 40px;
  }

  .desc {
    font-size: 14px;
    line-height: 24px;
    color: #777;
    padding-top: 8px;
  }

  .demo {
    box-sizing: border-box;
    border: 1px solid #e4e7ef;
    width: 99%;
    // height: 530px;
    margin-top: 24px;
    padding-bottom: 20px;

    .demo-result,
    .demo-code {
      box-sizing: border-box;
      padding: 24px;
      float: left;
      height: 100%;
    }

    .demo-result {
      .result-title {
        font-size: 18px;
        line-height: 24px;
        color: #222;
      }

      .result_form {
        width: 60%;
        margin: 72px auto 0;
      }

      .result_input {
        width: 100%;
        border: 1px solid #e4e7ef;
        height: 40px;
        line-height: 38px;
        padding-left: 16px;
        box-sizing: border-box;
        margin-bottom: 16px;
        font-size: 18px;
        color: #abaeb2;
        background-color: transparent;
      }

      .result_btn {
        border: 0;
        outline: 0;
        width: 100%;
        height: 40px;
        line-height: 40px;
        text-align: center;
        font-size: 18px;
        color: #fff;
        background: #0a4bee;
        cursor: pointer;
        margin-top: 15px;
      }
    }

    .demo-code {
      background: #f7f9fa;
      position: relative;

      .code-title {
        float: left;
        font-size: 18px;
        line-height: 24px;
        color: #222;
      }

      .code_copy {
        float: right;
        width: 68px;
        height: 24px;
        line-height: 24px;
        border-radius: 12px;
        background: #6f7482;
        color: #fff;
        font-size: 12px;
        outline: none;
        border: none;
        cursor: pointer;
      }

      .code-container {
        padding-top: 20px;
        display: block;
        overflow: auto;
        color: #4d4d4c;
        padding: 0.5em;
        line-height: 1.5;
      }
    }
  }
}
</style>
