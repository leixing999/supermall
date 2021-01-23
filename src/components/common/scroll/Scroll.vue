<template>
  <div class="wrapper" ref="wrapper">
    <div >
      <slot></slot>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'Scroll',
  data() {
    return {
      scroll: null,
    }
  },
  mounted() {
    this.scroll = new BScroll(this.$refs.wrapper, {
      click: true,
      probeType: 2,
    }).on('scroll', (options) => {
      console.log(options)
    })
  },
}
</script>

<style scoped>
</style>