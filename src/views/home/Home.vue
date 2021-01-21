<template>
  <div id="home">
    <div class="home-nav">
      <nav-bar>
       <div slot="center" backgroudcolor="blue">购物街</div>
      </nav-bar>
       <div>
         <home-swiper :swiperData="banners"></home-swiper>
       </div>
       <div>
         <recommend-view :recommends="recommends"></recommend-view>
       </div>
    </div>
    
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import HomeSwiper from './homeComponents/HomeSwiper'
import RecommendView from './homeComponents/RecommendView'
import { getHomeMultidata } from 'network/home'
export default {
  name: 'Home',
  components: { NavBar, HomeSwiper, RecommendView },
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
    })
  },
}
</script>

<style>
.home-nav {
  background-color: rgb(148, 29, 128);
  color: white;
}
</style>