<template>
  <div class="container">
    <div class="info" 
        :class="{'active': infoIsVisible === true}"
        v-observe-visibility="{
          callback: infoVisibilityChanged,
          throttle: 300
        }">
      <h1 class="title">服务类型</h1>
      <p class="description">Moving Service</p>
    </div>
    <div class="line"
        :class="{'active': line1IsVisible === true}"
        v-observe-visibility="{
          callback: line1VisibilityChanged,
          throttle: 300
        }">
      <div class="cell xjbj">
        <span>小件搬家</span>
        <img src="http://www.chinaant.net/resources/img/xjkb@2x.png">
        <button>立即预约</button>
      </div>
      <div class="cell ptbj">
        <span>普通搬家</span>
        <img src="http://www.chinaant.net/resources/img/ptbj@2x.png">
        <button>立即预约</button>
      </div>
      <div class="cell ctbj">
        <span>长途搬家</span>
        <img src="http://www.chinaant.net/resources/img/ctbj@2x.png">
        <button>立即预约</button>
      </div>
      <div class="cell jpbj">
        <span>精品搬家</span>
        <img src="http://www.chinaant.net/resources/img/jpbj@2x.png">
        <button>立即预约</button>
      </div>
    </div>
    <div class="line"
        :class="{'active': line2IsVisible === true}"
        v-observe-visibility="{
          callback: line2VisibilityChanged,
          throttle: 300
        }">
      <div class="cell swbj">
        <span>涉外搬家</span>
        <img src="http://www.chinaant.net/resources/img/hwbj@2x.png">
        <button>立即预约</button>
      </div>
      <div class="cell sbby">
        <span>设备搬运</span>
        <img src="http://www.chinaant.net/resources/img/sbby@2x.png">
        <button>立即预约</button>  
      </div>
      <div class="cell bgsbq">
        <span>公室搬迁</span>
        <img src="http://www.chinaant.net/resources/img/bgsbq@2x.png">
        <button>立即预约</button>  
      </div>
      <div class="cell zzfw">
        <span>增值服务</span>
        <img src="http://www.chinaant.net/resources/img/zzfw@2x.png">
        <button>立即预约</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Service",
  data() {
    return {
      infoIsVisible: false,
      line1IsVisible: false,
      line2IsVisible: false
    }
  },
  methods: {
    infoVisibilityChanged(isVisible, entry) {
      if(isVisible) {
        this.infoIsVisible = isVisible;
      }
    },
    line1VisibilityChanged(isVisible, entry) {
      if(isVisible) {
        this.line1IsVisible = isVisible;
      }
    },
    line2VisibilityChanged(isVisible, entry) {
      if(isVisible) {
        this.line2IsVisible = isVisible;
      }
    }
  }
}
</script>

<style lang="postcss" scoped>
$animationSeconds: 0.3s;

.container {
  background: white;
  padding-bottom: 50px;
  padding-top: 100px;
}

.info {
  width: 100%;
  text-align: center;
  opacity: 0;
  
  &.active {
    animation: fadeInUp 1.5s;
    opacity: 1;
  }
  
  .title {
    font-size: 36px;
    font-weight: 500;
    color: #676767;
  }

  .description {
    font-size: 14px;
    margin-top: 10px;
    margin-bottom: 60px;
    color: #d8d8d8;
  }
}

.line {
  display: flex;
  opacity: 0;

  &.active {
    opacity: 1;
    .cell {
      animation: zoomIn 0.8s;
    }
  }

  & ~ .line {
    margin-top: 80px;
  }

  .cell {
    flex: 1 1;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: white;
    font-size: 19px;
    font-weight: bold;
    height: 240px;
    border-radius: 4px;
    display: flex;

    & ~ .cell {
      margin-left: 45px;
    }

    button {
      background: #fc0;
      padding: 1px 3px;
      width: 82px;
      height: 34px;
      line-height: 34px;
      text-align: center;
      color: white;
      font-size: 14px;
      border: none;
      border-radius: 3px;
      display: none;
      transition: color 0.3s;
    }
    
    &:hover {
      position: relative;
      transition: background-size $animationSeconds ease-in-out;

      img {
        width: 100px;
        height: 100px;
        padding: 25px;
        border-radius: 50px;
        position: absolute;
        top: -50px;
        margin-top: 0;
      }

      button {
        display: block;
        margin-top: 20px;

        &:hover {
          color: #333;
          cursor: pointer;
        }

        &:focus {
          outline: none;
        }
      }

      span {
        animation: fadeInBottom $animationSeconds;
      }
    }

    img {
      width: 80px;
      height: 80px;
      margin-top: 30px;
    }

    button {
      animation: fadeInUpBig $animationSeconds;
    }

    &.xjbj {
      background: #ea7719 url(http://www.chinaant.net/resources/img/active/xjkb@2x.gif) no-repeat;
      background-size: 0 0;
      background-position: 50% 50%;
      &:hover {
        background-size: 100% 100%;
        img {
          background: #ea7719;
        }
      }
    }

    &.ptbj {
      background: #20c0a0 url(http://www.chinaant.net/resources/img/active/ptbj@2x.gif) no-repeat;
      background-size: 0 0;
      background-position: 50% 50%;
      &:hover {
        background-size: 100% 100%;
        img {
          background: #20c0a0;
        }
      }
    }

    &.ctbj {
      background: #4a90e2 url(http://www.chinaant.net/resources/img/active/bg_ctbj@2x.gif) no-repeat;
      background-size: 0 0;
      background-position: 50% 50%;
      &:hover { 
        background-size: 100% 100%;
        img {
          background: #4a90e2;
        }
      }
    }

    &.jpbj {
      background: #455e72 url(http://www.chinaant.net/resources/img/active/jpbj@2x.gif) no-repeat;
      background-size: 0 0;
      background-position: 50% 50%;
      &:hover {
        background-size: 100% 100%;
        img {
          background: #455e72;
        }
      }
    }

    &.swbj {
      background: #455e72 url(http://www.chinaant.net/resources/img/active/swbj@2x.gif) no-repeat;
      background-size: 0 0;
      background-position: 50% 50%;
      &:hover {
        background-size: 100% 100%;
        img {
          background: #455e72;
        }
      }
    }

    &.sbby {
      background: #4a90e2 url(http://www.chinaant.net/resources/img/active/sbby@2x.gif) no-repeat;
      background-size: 0 0;
      background-position: 50% 50%;
      &:hover {
        background-size: 100% 100%;
        img {
          background: #4a90e2;
        }
      }
    }

    &.bgsbq {
      background: #20c0a0 url(http://www.chinaant.net/resources/img/active/bgsbq@2x.gif) no-repeat;
      background-size: 0 0;
      background-position: 50% 50%;
      &:hover {
        background-size: 100% 100%;
        img {
          background: #20c0a0;
        }
      }
    }

    &.zzfw {
      background: #ea7719 url(http://www.chinaant.net/resources/img/active/zzfw@2x.gif) no-repeat;
      background-size: 0 0;
      background-position: 50% 50%;
      &:hover {
        background-size: 100% 100%;
        img {
          background: #ea7719;
        }
      }
    }
  }
}

@keyframes fadeInBottom {
  from {
    opacity: 0;
    transform: translate3d(0, -100%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translate3d(0, 100%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

@keyframes fadeInUpBig {
  from {
    opacity: 0;
    transform: translate3d(0, 300%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

@keyframes zoomIn {
  from {
    opacity: 0;
    transform: scale3d(0.3, 0.3, 0.3);
  }

  50% {
    opacity: 1;
    transform: scale3d(1.1, 1.1, 1.1);
  }

  80% {
    transform: scale3d(0.95, 0.95, 0.95);
  }
}
</style>
