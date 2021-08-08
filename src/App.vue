<template>
  <div id="app">
    <button @click="openPop()">打开弹窗</button>
    <pop-box ref="pop" v-if="popFlag" :popData="popData" @closePop="closePop"></pop-box>
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
        cancleBtn: "取消",
        confirmBtn: "确定",
      },
      popFlag: false,
    };
  },
  methods: {
    openPop(){
      this.popFlag=true
    },
    closePop(val) {
      switch(val.type){
        case 0:
          this.popFlag=false
          break;
        case 1:
          this.popFlag=false
          break;
      }
    },
  },
};
</script>

<style>
</style>
