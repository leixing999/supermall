<template>
  <div id="home">
    <div class="home-nav">
      <nav-bar>
      <div slot="center" backgroudcolor="blue">购物街</div>
      </nav-bar>
    </div>
   <scroll class="content">
      <home-swiper :swiperData="banners"></home-swiper>
      <recommend-view :recommends="recommends"></recommend-view>
      <home-feature-view></home-feature-view>
      <tab-control class="tabControlClsass" :tabItems="['流行','新款','精选']"></tab-control>
   </scroll>
  
  </div>
</template>

<script>
/********home子组件加载************ */
import HomeSwiper from './homeComponents/HomeSwiper'
import RecommendView from './homeComponents/RecommendView'
import HomeFeatureView from './homeComponents/HomeFeatureView'
/*********home用到的公共组件******** */
import NavBar from 'components/common/navbar/NavBar'
import TabControl from 'components/common/tabcontrol/TabControl'
import Scroll from 'components/common/scroll/Scroll'
/*********home组件调用方法接口*********** */
import { getHomeMultidata } from 'network/home'
export default {
  name: 'Home',
  components: {
    HomeSwiper,
    RecommendView,
    HomeFeatureView,

    NavBar,
    TabControl,
    Scroll,
  },
  data() {
    return {
      banners: [],
      recommends: [],
    }
  },
  created() {
    getHomeMultidata().then((res) => {
      this.banners = res.data.banner.list
      this.recommends = res.data.recommend.list
      console.log(res.data)
    })
  },
  mounted() {},
}
</script>

<style scoped>
#home {
  /* padding-top: 44px; */
  position: relative;
  height: 100vh;
}
.home-nav {
  background-color: rgb(148, 29, 128);
  color: white;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}
.tabControlClsass {
  position: sticky;
  top: 44px;
}
.content {
  position: absolute;
  overflow: hidden;
  top: 44px;
  bottom: 49px;
  left: 0;
  right: 0;
}
</style>