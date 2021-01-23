<template>
  <div>
     <swiper>
       <swiper-item>
         <div slot="imgBoxSlot">
          <ul>
              <li v-for="(item,index) in swiperData" class="imgList" :key="index" :style="{display: index===currentIndex ? 'block' : 'none'}" >
                <a :href="item.link">
                  <img :src="item.image" alt="" >
                </a>
              </li>
            </ul>
         </div>
         <div slot="numBoxSlot">
            <div class="nums" v-for="(item,index) in swiperData" :key="index" @click="btnClick(index)" :style="{background: index===currentIndex ?  ' rgba(0, 255, 106, 0.767)':'blue'}">
               {{index+1}}
         </div>
         </div>
       </swiper-item>
     </swiper>

  </div>
</template>

<script>
import Swiper from 'components/common/swiper/Swiper'
import SwiperItem from 'components/common/swiper/SwiperItem'

export default {
  name: 'HomeSwiper',
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
  },
  methods: {
    btnClick(index) {
      this.currentIndex = index
    },
  },
  components: {
    Swiper,
    SwiperItem,
  },
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
li {
  list-style: none;
}

.imgList {
  position: absolute;
  display: none;
}
.imgList img {
  width: 100%;
  vertical-align: middle;
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