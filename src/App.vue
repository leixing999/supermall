<template>
  <div id="app">
     <nav-bar/>
    <router-view/>
   
   <main-tab-bar/>
  </div>
</template>

<script>
import MainTabBar from 'components/content/mainTabbar/MainTabBar'
import NavBar from 'components/common/navbar/NavBar'
export default {
  name: 'App',
  components: { MainTabBar, NavBar },
  methods: {},
}
</script>

<style>
@import 'assets/css/base.css';
</style>
