<template>
    <div>
        <div class="title">热销推荐</div>
        <ul class="items">
            <li class="item bo" v-for="item of recommendList" :key="item.id">
                    <img class="item-img" :src="item.imgURL" alt="">            
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  name: "HomeRecommend",
  data(){
      return{
          recommendList:[{
              id:'0001',
              imgURL:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
              title:'北京温泉排行榜',
              desc:'细数北京温泉，温暖你的冬天'
          },{
              id:'0002',
              imgURL:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
              title:'北京温泉排行榜',
              desc:'细数北京温泉，温暖你的冬天'
          },{
              id:'0003',
              imgURL:'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
              title:'北京温泉排行榜',
              desc:'细数北京温泉，温暖你的冬天'
          }]
      }
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

.item {
    display: flex;
    height: 1.9rem;
    overflow: hidden;

    .item-img {
        width: 1.7rem;
        height: 1.7rem;
        padding: 0.1rem;
    }

    .item-info {
        flex: 1;
        padding :.1rem
    }
    .item-title{
        line-height :.54rem
        font-size :.32rem
    }
    .item-desc{
        line-height :.4rem
        color :#ccc
    }
    .item-button{
        line-height :.44rem
        margin-top :.16rem
        color :#fff
        background :#ff9300
        padding :0 .2rem
        border-radius :.06rem
    }

}
</style>

