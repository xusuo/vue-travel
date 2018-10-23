<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul class="items">
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgURL" alt="">            
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: "HomeWeekend",
  data() {
    return {
      recommendList: [
        {
          id: "0001",
          imgURL:
            "http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg",
          title: "北京温泉排行榜",
          desc: "细数北京温泉，温暖你的冬天"
        },
        {
          id: "0002",
          imgURL:
            "http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg",
          title: "北京温泉排行榜",
          desc: "细数北京温泉，温暖你的冬天"
        },
        {
          id: "0003",
          imgURL:
            "http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg",
          title: "北京温泉排行榜",
          desc: "细数北京温泉，温暖你的冬天"
        }
      ]
    };
  }
};
</script>
<style lang="stylus" scoped>
.title {
    margin-top: 0.2rem;
    line-height: 0.8rem;
    background: #eee;
    text-indent: 0.2rem;
}


.item-img-wrapper{
    height :0;
    overflow :hidden
    padding-bottom :33.9% 

    .item-img {
        width: 100%;
    }   

}
.item-info {
        padding: 0.1rem;
    }

    .item-title {
        line-height: 0.54rem;
        font-size: 0.32rem;
    }

    .item-desc {
        line-height: 0.4rem;
        color: #ccc;
    }
</style>

