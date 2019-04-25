<template>
  <div class="container">
    <div class="form">
      <div class="field">
        <img src="http://www.chinaant.net/resources/img/chufa_icon_n@2x.png">
        <input type="text" placeholder="请输入出发地点" autocomplete="off">
      </div>
      <div class="field">
        <img src="http://www.chinaant.net/resources/img/daoda_icon_n@2x.png">
        <input type="text" placeholder="请输入到达地点" autocomplete="off">
      </div>
      <button>立即估价</button>
    </div>
    <div class="index">
      <div class="one">
        <div class="number">36</div>
        <p class="cate">全国分公司</p>
        <p class="detail">蚂蚁搬家公司全国覆盖网点</p>
      </div>
      <div class="one">
        <div class="number">1000000</div>
        <p class="cate">行业经验</p>
        <p class="detail">搬家配送经验积累，服务千万客户</p>
      </div>
      <div class="one">
        <div class="number">3000</div>
        <p class="cate">搬家员工</p>
        <p class="detail">岗前培训考核，保证服务品质</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "OrderCard"
}
</script>

<style scoped lang="postcss">
$formHeight: 86px;
$shadowColor: #a4bcf6;
$numberColor: #003894;

.container {
  margin-top: -$formHeight;
  box-shadow: -20px 30px 20px -20px $shadowColor, 20px 30px 20px -20px $shadowColor;
  position: relative;
  z-index: 1;
  animation: fadeInUp 1s;
}

.form {
  width: 100%;
  height: $formHeight;
  border: 3px solid #EEE;
  border-radius: 5px;
  background: white;
  display: flex;
  justify-content: space-between;
  align-items: center;

  .field {
    height: 40px;
    display: flex;
    align-items: center;

    img {
      margin: 0 40px 0 100px;
      height: 100%;
    }

    input {
      width: 250px;
      height: 100%;
      font-size: 18px;
      border: none;
      text-align: center;

      &::placeholder {
        color: #CCC;
      }

      &:focus {
        outline: none;
      }
    }
  }

  button {
    color: white;
    background: #fc0;
    border: none;
    width: 165px;
    height: 100%;
    font-size: 20px;
    font-weight: bold;

    &:hover {
      background: #edbd00;
      cursor: pointer;
    }

    &:focus {
      outline: none;
    }
  }
}

.index {
  width: 100%;
  height: 290px;
  background: white url("http://www.chinaant.net/resources/img/topbg.png") no-repeat;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-size: 300px;
  background-position: center top;

  .one {
    flex: 1 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    & > * ~ * {
      margin-top: 20px;
    }

    .number {
      color: $numberColor;
      font-size: 50px;
      font-weight: bold;

      &::after {
        content: "";
        display: block;
        width: 40px;
        height: 1px;
        background: $numberColor;
        margin: 0 auto;
      }
    }

    .cate {
      color: #555;
      font-size: 18px;
      font-weight: bold;
    }

    .detail {
      color: #b6b6b6;
      font-size: 15px;
    }
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translate3d(0, 10%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}
</style>
