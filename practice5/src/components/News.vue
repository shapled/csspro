<template>
  <div class="container"
    :class="{'active': newsIsVisible === true}"
    v-observe-visibility="{
      callback: newsVisibilityChanged,
      throttle: 300
    }">
    <div class="show">
      <img src="http://www.chinaant.net/resources/img/pt@2x.png">
    </div>
    <div class="articles">
      <h3>综合咨询</h3>
      <a class="line" href="#">成都空调清洗价格</a>
      <a class="line" href="#">广州长途搬家公司的收费标准你知道吗？</a>
      <a class="line" href="#">怎样选择专业的广州长途搬家公司？</a>
      <a class="line" href="#">济南搬家公司哪家好？</a>
      <a class="line" href="#">怎么清洗空调？</a>
    </div>
    <div class="articles">
      <h3>蚂蚁动态</h3>
      <a class="line" href="#">清明扫墓，我们不“蚁”样</a>
      <a class="line" href="#">请善待5%的投诉，你将得到100%的回报</a>
      <a class="line" href="#">来蚂蚁集团工作，高薪有了、另一半也有了</a>
      <a class="line" href="#">蚂蚁总裁的春培分享：如何实现人生的第一次财务自由</a>
      <a class="line" href="#">龙抬头，蚂蚁集团邀请你来“桥下剃头”</a>
    </div>
    <div class="articles">
      <h3>搬家吉日</h3>
      <a class="line" href="#">贵阳蚂蚁专业化的搬家服务，让你搬家快又安全</a>
      <a class="line" href="#">2019年8月搬家黄道吉日</a>
      <a class="line" href="#">2019年7月搬家黄道吉日</a>
      <a class="line" href="#">2019年6月搬家黄道吉日</a>
      <a class="line" href="#">2019年5月搬家黄道吉日</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "News",
  data() {
    return {
      newsIsVisible: false
    }
  },
  methods: {
    newsVisibilityChanged(isVisible, entry) {
      if(isVisible) {
        this.newsIsVisible = isVisible;
      }
    }
  }
}
</script>

<style scoped lang="postcss">
.container {
  margin: 100px auto;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  opacity: 0;
  transition: opacity 0.8s;

  &.active {
    opacity: 1;
    animation: fadeInBottom 0.8s;
  }

  & > * {
    width: 233px;
    flex: 0 1 0;
  }

  .show {
    padding-left: 15px;
    padding-right: 15px;

    img {
      width: 260px;
      /* width: 100%; */
    }
  }

  .articles {
    & > * {
      display: block;
    }

    h3 {
      color: #2679ee;
      font-size: 18px;
      font-weight: bold;
      line-height: 3em;
    }

    .line {
      white-space: nowrap; 
      overflow: hidden;
      text-overflow: ellipsis;
      color: gray;
      text-decoration: none;
      line-height: 2.2em;

      &:hover {
        text-decoration: underline;
      }

      &::before {
        content: "";
        display: inline-block;
        background: #3B8CC4;
        width: 10px;
        height: 10px;
        border-radius: 5px;
        margin-right: 0.8em;
      }
    }
  }
}

@keyframes fadeInBottom {
  from {
    opacity: 0;
    transform: translate3d(0, -20%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
</style>
