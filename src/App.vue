<template>
  <div id="app">
    <button @click="openPop()">打开弹窗</button>
    <pop-box ref="pop" :popData="popData"></pop-box>
  </div>
</template>

<script>
import popBox from "./components/pop.vue";
export default {
  name: "App",
  components: {
    popBox,
  },
  data() {
    return {
      popData: {
        title: "提示",
        content: "此操作将永久删除文件，是否继续？",
        confirmBtn: "确定",
      },
      popFlag: false,
    };
  },
  methods: {
    openPop() {
      this.$refs.pop.openPop();
    },
  },
};
</script>

<style>
</style>
