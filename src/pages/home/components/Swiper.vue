<template>
    <swiper :options="swiperOption">
    <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgURL" alt="">
    </swiper-slide>   
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>
<script>
export default {
  name: "HomeSwiper",
  data() {
    return {
      swiperOption: {
          pagination:'.swiper-pagination',
          loop:true,
          autoplay:2000
      },
      swiperList:[{
          id:'0001',
          imgURL:"http://img1.qunarzz.com/piao/fusion/1809/31/da037478f37cf202.jpg_750x200_a02cf862.jpg"
      },{
          id:'0002',
          imgURL:"http://img1.qunarzz.com/piao/fusion/1610/f3/f39d9de1e92deb02.jpg_750x200_8cbc3f9b.jpg"
      }]
    };
  }
};
</script>

<style lang='stylus' scoped>
.swiper-img
    width 100%
</style>

