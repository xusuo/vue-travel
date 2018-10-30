<template>
    <ul class="list">
        <li
          class="item"
          v-for="item of letters"
          :key="item"
          :ref="item"
          @touchstart="handleStart"
          @touchmove="handleMove"
          @touchend="handleEnd"
          @click="handleClick"
        >{{item}}</li>
    </ul>
</template>
<script>
export default {
  name: "CityAlphabet",
  props: {
    cities: Object
  },
  computed: {
    letters() {
      const letters = [];
      for (let i in this.cities) {
        letters.push(i);
      }
      return letters;
    }
  },
  data() {
    return {
      touch: false
    };
  },
  methods: {
    handleClick(e) {
      this.$emit("change", e.target.innerText);
    },
    handleStart() {
      this.touch = true;
    },
    handleMove(e) {
      if (this.touch) {
        const staetY = this.$refs["A"][0].offsetTop;
        const touchY = e.touches[0].clientY - 79;
        const index = Math.floor((touchY - staetY) / 20);
        if (index >= 0 && index < this.letters.length) {
          this.$emit("change", this.letters[index]);
        }
      }
    },
    handleEnd() {
      this.touch = false;
    }
  }
};
</script>
<style lang="stylus" scoped>
.list {
    position: absolute;
    top: 1.58rem;
    right: 0;
    bottom: 0;
    width: 0.4rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-self: center;

    .item {
        line-height: 0.4rem;
        text-align: center;
        color: #00bcd4;
    }
}
</style>
