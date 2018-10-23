<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img">
                    <img class="icon-img-content" :src="item.imgURL" alt="">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
             </swiper-slide>
        </swiper>
    
    </div>
</template>
<script>
export default {
  name: "HomeIcons",
  data() {
    return {
      swiperOption: {
          autoplay:false
      },
      iconList: [
        {
          id: "0001",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        },
        {
          id: "0002",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        },
        {
          id: "0003",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        },
        {
          id: "0004",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        },
        {
          id: "0005",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        },
        {
          id: "0006",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        },
        {
          id: "0007",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        },
        {
          id: "0008",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        },
        {
          id: "0009",
          imgURL:
            "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
          desc: "景点门票"
        }
      ]
    };
  },
  computed: {
    pages() {
      const pages = [];
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8);
        if (!pages[page]) {
          pages[page] = [];
        }
        pages[page].push(item);
      });
      return pages;
    }
  }
};
</script>

 <style lang="stylus" scoped>
 .icons >>> .swiper-container {
     height: 0;
     padding-bottom: 50%;
 }
.icons
  margin-top :.1rem
  .icon {
      position: relative;
      overflow: hidden;
      width: 25%;
      float: left;
      height: 0;
      padding-bottom: 25%;

      .icon-img {
          position: absolute;
          top: 0;
          left: 0;
          right: 0;
          bottom: 0.44rem;

          .icon-img-content {
              display: block;
              margin: 0 auto;
              height: 100%;
          }
      }

      .icon-desc {
          position: absolute;
          left: 0;
          right: 0;
          bottom: 0;
          line-height: 0.44rem;
          height: 0.44rem;
          color: #333;
          text-align: center;
      }
 }
</style>


