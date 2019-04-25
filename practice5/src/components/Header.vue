<template>
  <header>
    <div class="container">
      <div class="clearfix">
        <div class="left">
          <div class="line">
            当前城市:[ 北京市 ] 
            <el-button plain size="mini" class="switch">
              <i class="el-icon-sort"></i>
              手动切换
            </el-button>
            <span class="bubble">
              切换获取当前城市报价
              <i class="el-icon-circle-close"></i>
            </span>
          </div>
        </div>
        <div class="right">
          <div class="line">
            <el-button type="text" id="login">登录</el-button>
            <el-dropdown id="accounts" placement="top">
              <span class="el-dropdown-link">
                个人中心<i class="el-icon-arrow-down el-icon--right"></i>
              </span>
              <el-dropdown-menu slot="dropdown">
                <el-dropdown-item>订单中心</el-dropdown-item>
                <el-dropdown-item>客服投诉</el-dropdown-item>
                <el-dropdown-item>退出登陆</el-dropdown-item>
              </el-dropdown-menu>
            </el-dropdown>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="postcss">
.el-popper {
  margin-top: 0;
}
</style>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="postcss">
$headerHeight: 47px;
$bubbleColor: #003894;
$borderColor: #DCDFE6;

header {
  font-size: 12px;

  height: $headerHeight;
  border-bottom: 1px solid #EEE;

  #login{
    color: #808080;
  }

  #accounts {
    margin-left: 1em;
    &:hover {
      cursor: pointer;
    }
  }

  .line {
    height: $headerHeight;
    line-height: $headerHeight;

    * {
      display: inline-block;
    }

    .switch{
      padding: 0.5em 0.8em;
      border-color: $borderColor;
      
      i {
        transform: rotate(90deg);
      }

      &:hover {
        color: $bubbleColor;
        border-color: $borderColor;
      }
    }
    /* button.switch {
      height: calc($headerHeight * 0.6);
      line-height: calc($headerHeight * 0.6);
      border: 1px solid #CCC;
      color: #999;
      background: transparent;
      padding: 0 0.5em;

      &:focus {
        outline: none;
      }
    } */

    .bubble {
      height: calc($headerHeight * 0.6);
      line-height: calc($headerHeight * 0.6);
      padding: 0 0.5em;
      color: white;
      background: $bubbleColor;
      position: relative;
      margin-left: 2em;
      animation: shake 20s infinite;
      
      i {
        &:hover {
          cursor: pointer;
        }
      }

      &::after {
        content: "";
        display: block;
        position: absolute;
        right: 100%;
        top: 30%;
        border-right: calc($headerHeight * 0.1) solid $bubbleColor;
        border-top: calc($headerHeight * 0.1) solid transparent;
        border-bottom: calc($headerHeight * 0.1) solid transparent;
        width: 0;
        height: 0;
      }
    }
  }
}

@keyframes shake {

  from,
  to {
    transform: translate3d(0, 0, 0);
  }

  10%,
  30%,
  50%,
  70%,
  90% {
    transform: translate3d(-5px, 0, 0);
  }

  20%,
  40%,
  60%,
  80% {
    transform: translate3d(5px, 0, 0);
  }
}
</style>
