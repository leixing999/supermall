<template>
    <tab-bar>
      <tab-bar-item path="/home" activeColor="red">
        <img src="~assets/img/tabbar/gw1.png" alt="" slot="item-icon">
        <img src="~assets/img/tabbar/gw2.png" alt="" slot="item-icon-active">
        <div  slot="item-text">首页</div>
      </tab-bar-item>
      <tab-bar-item path="/category" activeColor="red">
        <img src="~assets/img/tabbar/gw1.png" alt="" slot="item-icon">
        <img src="~assets/img/tabbar/gw2.png" alt="" slot="item-icon-active">

        <div  slot="item-text">分类</div>
      </tab-bar-item>
      <tab-bar-item path="/cart" activeColor="red">
        <img src="~assets/img/tabbar/gw1.png" alt="" slot="item-icon">
        <img src="~assets/img/tabbar/gw2.png" alt="" slot="item-icon-active">

        <div  slot="item-text">购物车</div>
      </tab-bar-item>
      <tab-bar-item path="/profile" activeColor="red">
        <img src="~assets/img/tabbar/gw1.png" alt="" slot="item-icon">
        <img src="~assets/img/tabbar/gw2.png" alt="" slot="item-icon-active">

        <div  slot="item-text">我的</div>
      </tab-bar-item>
      
    </tab-bar>
</template>

<script>
import TabBar from 'components/common/tabbar/TabBar'
import TabBarItem from 'components/common/tabbar/TabBarItem'
export default {
  name: 'TabBarApp',
  components: { TabBar, TabBarItem },
}
</script>

<style scoped>
</style>