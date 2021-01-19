<template>
  <div>
    <h2>Category</h2>
    <h1>1111{{powerCounter}}</h1>
  </div>
</template>

<script>
export default {
  name: 'Category',
  computed: {
    powerCounter() {
      return this.$store.getters.powerCounter
    },
  },
}
</script>

<style>
</style>