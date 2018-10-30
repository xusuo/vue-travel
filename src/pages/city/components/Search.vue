<template>
<div>
    <div class="search">
        <input
        v-model="keyword"
        class="search-input"
        type="text"
        placeholder="输入城市或拼音">
    </div>
    <div class="search-content" ref="wrapper" v-show="keyword">
        <ul>
            <li 
              class="search-item"
              v-for="item of list"
              :key="item.id"
              @click="handleCityClick(item.name)">{{item.name}}</li>
        </ul>
    </div>
</div>
</template>

<script>
import BetterScroll from "better-scroll";
export default {
  name: "CitySearch",
  props: {
    cities: Object
  },
  data() {
    return {
      keyword: "",
      list: [],
      timer: null
    };
  },
  methods:{
      handleCityClick(city){
          this.$store.commit('changeCity',city)
          this.$router.push('/')
      }
  },
  watch: {
    keyword() {
      if (this.timer) {
        clearTimeout(this.timer);
      }
      if (!this.keyword) {
        this.list = [];
        return;
      }
      this.timer = setTimeout(() => {
        const result = [];
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (
                value.spell.indexOf(this.keyword) != -1 ||
                value.name.indexOf(this.keyword) != -1
              ) {
                  result.push(value);
               }
          });
        }
        this.list = result;
      }, 100);
    }
  },
  mounted() {
    this.scroll = new BetterScroll(this.$refs.wrapper);
  }
};
</script>
<style lang="stylus" scoped>
.search {
  height: 0.72rem;
  padding: 0 0.1rem;
  background: #00bcd4;

  .search-input {
    box-sizing: border-box;
    height: 0.62rem;
    width: 100%;
    text-align: center;
    line-height: 0.62rem;
    padding: 0 0.1rem;
  }
}

.search-content {
  overflow: hidden;
  z-index: 1;
  position: absolute;
  top: 1.58rem;
  bottom: 0;
  left: 0;
  right: 0;
  background: #eee;

  .search-item {
    line-height: 0.62rem;
    padding-left: 0.2rem;
    background: #fff;
    color: #666;
  }
}
</style>
