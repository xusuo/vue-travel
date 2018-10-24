<template>    
    <div class="header">
        城市选择        
        <div class="iconfont header-back">&#xe624;</div>
    </div>
</template>
<script>
export default {
    name:'CityHeader'
}
</script>
<style lang="stylus" scoped>
    .header{
        position :relative
        overflow :hidden
        text-align :center
        color :#fff
        background :#00bcd4
        height :.86rem
        line-height :.86rem
        font-size  :.32rem
        .header-back{
            position :absolute
            width :.64rem
            font-size :.4rem
            top :0
            left :0
            color :#fff
        }
    }
</style>

