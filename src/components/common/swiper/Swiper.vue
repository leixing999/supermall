<template>
  <div class="swiper">
     <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'Swiper',
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
li {
  list-style: none;
}
.swiper {
  height: 165px;
  margin: 0 auto;
}
</style>