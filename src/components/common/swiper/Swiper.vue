<template>
  <div class="swiper">
    <div class="imgBox">
      <!-- <a :href="link"><img :src="image" alt=""></a> -->
      <ul>
        <li v-for="(item,index) in swiperData" class="imgList" :key="index" :style="{display: index===currentIndex ? 'block' : 'none'}" >
          <a :href="item.link">
             <img :src="item.image" alt="" >
          </a>
        </li>
      </ul>
    </div>

    <div class="numBox">
      <div class="nums" v-for="(item,index) in swiperData" :key="index" @click="btnClick(index)" :style="{background: index===currentIndex ?  ' rgba(0, 255, 106, 0.767)':'blue'}">
        {{index+1}}
      </div>
     
    </div>
     
  </div>
</template>

<script>
export default {
  name: 'Swiper',
  props: {
    swiperData: {
      type: Array,
      default() {
        return []
      },
    },
  },
  data() {
    return {
      currentIndex: 0,
      preIndex: 0,
      nextIndex: 0,
      isActive: false,
    }
  },
  computed: {
    link() {
      /******异步导致数据没有加载的时候返回空值******* */
      if (this.swiperData.length === 0) {
        return ''
      }
      return this.swiperData[this.currentIndex].link
    },
    image() {
      /******异步导致数据没有加载的时候返回空值******* */
      if (this.swiperData.length === 0) {
        return ''
      }
      return this.swiperData[this.currentIndex].image
    },
    activeStyle() {
      return ''
    },
  },
  methods: {
    btnClick(index) {
      this.currentIndex = index
    },
  },
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

.imgBox {
  height: 150px;
  margin: 1px auto;
}
.imgList {
  position: absolute;
  display: none;
}
.imgList img {
  width: 100%;
  vertical-align: middle;
}

.numBox {
  display: flex;
  border-radius: 18px;
  height: 20px;
  margin-top: -10px;
  margin-left: 50%;
  position: fixed; /*让数字框浮动在图片层上*/
  text-align: center;
  color: white;
}
.nums {
  display: inline-block;
  width: 20px;
  height: 20px;
  border-radius: 18px;
  margin-right: 20px;
  text-align: center;
  vertical-align: middle;
}
</style>