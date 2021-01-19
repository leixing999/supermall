<template>
  <div id="home">
    <div class="home-nav">
      <nav-bar>
       <div slot="center" backgroudcolor="blue">购物街</div>
      </nav-bar>
    </div>
    
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar'

export default {
  name: 'Home',
  components: { NavBar },
}
</script>

<style>
.home-nav {
  background-color: rgb(148, 29, 128);
  color: white;
}
</style>