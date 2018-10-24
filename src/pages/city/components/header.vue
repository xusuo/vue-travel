<template>
    <div class="header">
        城市详情
        <router-link to="/">
            <div class="iconfont back-icon">&#xe624;</div>
        </router-link>
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
    height :.86rem
    line-height :.86rem
    background :#00bcd4
    font-size :.32rem
    text-align :center
    color :#fff
    .back-icon{
        position :absolute
        top: 0
        left :0
        width :.64rem
        font-size :.4rem
        color :#fff
    }
}
</style>