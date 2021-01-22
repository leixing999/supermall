<template>
  <div class="tabcontrol">
    
    <div v-for="(item,index) in tabItems" :key="index" class="tabcontrol-item" 
      :class="{active: currentIndex===index }" @click="btnClick(index)">
      <span >{{item}}</span>
    </div>
   
  </div>
</template>

<script>
export default {
  name: 'TabControl',
  props: {
    tabItems: {
      type: Array,
      default() {
        return []
      },
    },
  },
  data() {
    return {
      currentIndex: 0,
    }
  },
  methods: {
    btnClick(index) {
      this.currentIndex = index
    },
  },
}
</script>

<style>
.tabcontrol {
  display: flex;
  text-align: center;
  font-size: 15px;
  background-color: #fff;
}
.tabcontrol-item {
  flex: 1;
  margin-top: 15px;
  margin-bottom: 10px;
}
.tabcontrol-item span {
}

.active {
  color: red;
}
.active span {
  border-bottom: 3px solid red;
  padding: 5px;
}
</style>