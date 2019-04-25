<template>
  <div id="app">
    <Header />
    <Nav />
    <Banner />
    <OrderCard />
    <Service />
    <SubBrand />
    <Case />
    <News />
    <Footer />
    <Copyright />
  </div>
</template>

<script>
// http://www.chinaant.net/
import Header from './components/Header.vue'
import Nav from "./components/Nav.vue"
import Banner from "./components/Banner.vue"
import OrderCard from "./components/OrderCard.vue"
import Service from "./components/Service.vue"
import SubBrand from "./components/SubBrand.vue"
import Case from "./components/Case.vue"
import News from "./components/News.vue"
import Footer from "./components/Footer.vue"
import Copyright from "./components/Copyright.vue"

export default {
  name: 'app',
  components: {
    Header,
    Nav,
    Banner,
    OrderCard,
    Service,
    SubBrand,
    Case,
    News,
    Footer,
    Copyright
  }
}
</script>

<style lang="postcss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.container {
  width: 1160px;
  margin: 0 auto;
}

.clearfix {
  overflow: hidden;

  .left {
    float: left;
  }

  .right {
    float: right;
  }
}
</style>
