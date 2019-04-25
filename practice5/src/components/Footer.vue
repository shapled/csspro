<template>
  <footer>
    <div class="container">
      <div class="base">
        <div class="item">
          <div class="left">
            <i class="el-icon-phone"></i>
          </div>
          <div class="right">
            <h3>全国服务热线</h3>
            <p>400-020-8181</p>
          </div>
        </div>
        <div class="item">
          <div class="left">
            <i class="el-icon-location"></i>
          </div>
          <div class="right">
            <h3>集团总部地址</h3>
            <p>成都市高新区科园南二路6号</p>
          </div>
        </div>
        <div class="item">
          <div class="left">
            <i class="el-icon-phone"></i>
          </div>
          <div class="right">
            <h3>成都总部热线</h3>
            <p>028-85314488</p>
          </div>
        </div>
        <div class="item">
          <div class="left">
            <i class="el-icon-news"></i>
          </div>
          <div class="right">
            <h3>全国投诉热线</h3>
            <p>400-020-8181</p>
          </div>
        </div>
      </div>
      <div class="about">
        <a href="#">关于蚂蚁</a>
        <a href="#">全国网点</a>
        <a href="#">综合咨询</a>
        <a href="#">工作机会</a>
        <a href="#">搬家服务</a>
      </div>
      <div class="friends">
        <span>友情链接:</span>
        <a href="#">同城货运</a>
        <a href="#">生活服务网</a>
        <a href="#">熊猫搬</a>
        <a href="#">好久搬</a>
        <a href="#">上海搬家公司</a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style lang="postcss" scoped>
footer {
  width: 100%;
  height: 250px;
  color: white;
  background: url(http://www.chinaant.net/resources/img/footer.png) no-repeat;

  .container {
    padding: 45px 10px 0 10px;
    .base {
      display: flex;
      justify-content: space-between;

      .item {
        display: flex;

        .left {
          width: 40px;
          height: 40px;
          line-height: 40px;
          font-size: 22px;
          border-radius: 20px;
          background: black;
          text-align: center;
        }
        
        .right {
          margin-left: 20px;

          h3 {
            font-size: 18px;
            font-weight: bold;
          }

          p {
            font-size: 14px;
            line-height: 2em;
          }
        }
      }
    }

    .about {
      margin-top: 30px;
      opacity: 0.8;
      font-size: 12px;
      
      a {
        display: inline-block;
        color: #DBDBDB;
        text-decoration: none;
      }

      a ~ a {
        &::before {
          content: "|";
          display: inline-block;
          color: #DBDBDB;
          width: 1px;
          height: 1em;
          line-height: 1em;
          margin: 0 10px;
        }
      }
    }

    .friends {
      margin-top: 30px;

      span {
        color: white;
        font-size: 14px;
        font-weight: bold;
      }

      a {
        display: inline-block;
        color: #DBDBDB;
        text-decoration: none;      
        opacity: 0.8;
        font-size: 12px;
      }

      a {
        &::before {
          content: " ";
          display: inline-block;
          width: 1px;
          height: 1em;
          line-height: 1em;
          margin: 0 10px;
        }
      }
    }
  }
}
</style>
