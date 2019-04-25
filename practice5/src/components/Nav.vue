<template>
  <nav class="container">
    <div class="line clearfix">
      <div class="left">
        <img src="http://www.chinaant.net/resources/img/Mlogo.jpg">
      </div>
      <div class="middle">
        <div class="menus">
          <el-button type="text">首页</el-button>
          <el-button type="text">在线下单</el-button>
          <el-dropdown>
            <span class="el-dropdown-link">
              车型介绍
              <!-- <i class="el-icon-arrow-down el-icon--right"></i> -->
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>小件快搬</el-dropdown-item>
              <el-dropdown-item>大型货车</el-dropdown-item>
              <el-dropdown-item>大型起重</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <el-dropdown>
            <span class="el-dropdown-link">
              产品服务
              <!-- <i class="el-icon-arrow-down el-icon--right"></i> -->
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>蚂蚁搬家</el-dropdown-item>
              <el-dropdown-item>蚂蚁起重</el-dropdown-item>
              <el-dropdown-item>车身广告</el-dropdown-item>
              <el-dropdown-item>空调搬运</el-dropdown-item>
              <el-dropdown-item>家具拆装</el-dropdown-item>
              <el-dropdown-item>蚂蚁配送</el-dropdown-item>
              <el-dropdown-item>人工服务</el-dropdown-item>
              <el-dropdown-item>迷你仓库</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <el-button type="text">服务案例</el-button>
          <el-dropdown>
            <span class="el-dropdown-link">
              全国网点
              <!-- <i class="el-icon-arrow-down el-icon--right"></i> -->
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>华北片区</el-dropdown-item>
              <el-dropdown-item>华东片区</el-dropdown-item>
              <el-dropdown-item>华南片区</el-dropdown-item>
              <el-dropdown-item>华中片区</el-dropdown-item>
              <el-dropdown-item>西北片区</el-dropdown-item>
              <el-dropdown-item>西南片区</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <el-dropdown>
            <span class="el-dropdown-link">
              搬家答疑
              <!-- <i class="el-icon-arrow-down el-icon--right"></i> -->
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>搬家解惑</el-dropdown-item>
              <el-dropdown-item>综合资讯</el-dropdown-item>
              <el-dropdown-item>蚂蚁动态</el-dropdown-item>
              <el-dropdown-item>搬家吉日</el-dropdown-item>
              <el-dropdown-item>生活妙招</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <el-dropdown>
            <span class="el-dropdown-link">
              关于我们
              <!-- <i class="el-icon-arrow-down el-icon--right"></i> -->
            </span>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>企业简介</el-dropdown-item>
              <el-dropdown-item>企业文化</el-dropdown-item>
              <el-dropdown-item>企业荣誉</el-dropdown-item>
              <el-dropdown-item>企业招聘</el-dropdown-item>
              <el-dropdown-item>合作伙伴</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
        </div>
      </div>
      <div class="right"
        v-observe-visibility="{
          callback: phoneVisibilityChanged
        }">
        <img src="http://www.chinaant.net/resources/img/tel.png">
      </div>
      <div class="phone-image" :class="{'active': phoneIsVisible === false}">
        <img src="http://www.chinaant.net/resources/img/tel.png">
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Nav",
  data() {
    return {
      phoneIsVisible: true
    }
  },
  methods: {
    phoneVisibilityChanged(isVisible, entry) {
      this.phoneIsVisible = isVisible;
    }
  }
}
</script>

<style scoped lang="postcss">
$navHeight: 90px;
$navColor: #4B4B4B;
$hoverColor: #003894;

.phone-image {
  position: fixed;
  right: 0;
  top: 40px;
  width: 200px;
  padding: 10px;
  box-shadow: 0 0 3px #AAA;
  z-index: 5;
  background: white;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
  opacity: 0;

  img {
    width: 100%;
    height: 100%;
  }

  &.active {
    opacity: 1;
    animation: fadeInLeft 0.8s ease-out;
  }
}

.line {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: $navHeight;
  border-bottom: 1px solid #EEE;

  .left {
    img {
      width: 165px;
      height: 50px;
    }
  }

  .middle {
    .menus > * {
      color: $navColor;
      display: inline-block;
      margin-left: 1em;

      &:hover {
        cursor: pointer;
        color: $hoverColor;
      }
    }
  }

  .right {
    img {
      width: 165px;
      height: 40px;
    }
  }
}

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translate3d(100%, 0, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
</style>