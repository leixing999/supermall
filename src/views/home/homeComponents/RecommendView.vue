<template>
  <div class="recommend">
    <div v-for="(item,index) in recommends" :key="index" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image">
      </a>
      <div>
        {{item.title}}
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'RecommendView',
  props: {
    recommends: {
      type: Array,
      default() {
        return []
      },
    },
  },
}
</script>

<style>
.recommend {
  display: flex;
  text-align: center;
  width: 100%;
  font-size: 12px;
  color: black;
  background-color: white;
  padding: 10px 0 20px;
  border-bottom: 8px solid #eee;
}
.recommend-item {
  flex: 1;
}
.recommend-item img {
  width: 70px;
  height: 70px;
  vertical-align: middle;
  margin-bottom: 10px;
}
</style>