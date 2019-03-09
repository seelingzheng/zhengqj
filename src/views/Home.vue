<template>
  <div class="home">
    <bg/>
    <div class="btn-box">
      <a
        class="item"
        target="_blank"
        @mouseover="showBoxs('cesium')"
        @mouseout="hideBoxs('cesium')"
        href="http://cv3.zhengqj.cc"
      >Cesium</a>
      <a
        class="item"
        target="_blank"
        @mouseover="showBoxs('three')"
        @mouseout="hideBoxs('three')"
        href="http://3v.zhengqj.cc"
      >Three</a>
      <a
        class="item"
        target="_blank"
        @mouseover="showBoxs('blog')"
        @mouseout="hideBoxs('blog')"
        href="https://www.jianshu.com/u/90d57601c766"
      >Blog</a>
    </div>
    <div
      class="show animated"
      v-if="showBox"
      :class="{'slideInLeft':showBox,'slideOutLeft':!showBox}"
    ></div>
  </div>
</template>

<script>
// @ is an alias to /src
import bg from "@/components/bg.vue";

export default {
  name: "index",
  data() {
    return {
      showBox: false
    };
  },
  components: {
    bg
  },
  methods: {
    showBoxs(type) {
      // this.showBox = true;
    },
    hideBoxs(type) {
      // this.showBox = false;
    }
  }
};
</script>
<style lang="scss" scoped>
a:link {
  text-decoration: none;
  color: white;
}
　　 a:active {
  text-decoration: blink;
}
　　 a:hover {
  text-decoration: underline;
}
　　 a:visited {
  text-decoration: none;
}
.btn-box {
  user-select: none;
  position: absolute;
  color: white;
  left: calc(100vw / 2);
  top: calc(100vh / 2);
  .item {
    cursor: pointer;
    color: wheat;
    margin: 4px;
  }
}
.show {
  position: absolute;
  background: red;
  left: 100px;
  top: calc(100vh / 4);
  width: 100px;
  height: 100px;
}
</style>

