<template>
    <swiper :options="swiperOption">
    <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="">
    </swiper-slide>   
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>
<script>
export default {
  name: "HomeSwiper",
  props:{
      list:Array
  },
  data() {
    return {
      swiperOption: {
          pagination:'.swiper-pagination',
          loop:true,
          autoplay:2000
      },
    };
  }
};
</script>

<style lang='stylus' scoped>
.swiper-img
    width 100%
</style>

