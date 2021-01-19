<template>
  <div>
    <h2>Home</h2>
    <h1>{{count}}</h1>
    <button @click="add">add</button>
     <button @click="sub">sub</button>
  </div>
</template>

<script>
export default {
  name: 'Home',
  methods: {
    add() {
      this.$store.commit('increment')
    },
    sub() {
      this.$store.commit('decrement')
    },
  },
  computed: {
    count() {
      return this.$store.state.counter
    },
  },
}
</script>

<style>
</style>