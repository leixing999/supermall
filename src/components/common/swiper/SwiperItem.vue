<template>
<div>
  <div class="imgBox">
    <slot name="imgBoxSlot"></slot>
  </div>
  <div class="numBox">
    <slot name="numBoxSlot"></slot>
  </div>
</div>
</template>

<script>
export default {
  name: 'SwiperItem',
}
</script>

<style>
.imgBox {
  height: 150px;
  margin: 1px auto;
}

.numBox {
  display: flex;
  border-radius: 18px;
  height: 20px;
  margin-top: -10px;
  margin-left: 50%;
  position: absolute; /*让数字框浮动在图片层上*/
  text-align: center;
  color: white;
}
</style>