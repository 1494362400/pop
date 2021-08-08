<template>
  <div id="app">
    <button @click="openPop()">打开弹窗</button>
    <pop-box ref="pop"></pop-box>
  </div>
</template>

<script>

import popBox from './components/pop.vue'
export default {
  name: 'App',
  components: {
    popBox
  },
  data(){
    return{
      popFlag:false
    }
  },
  methods:{
    openPop(){
      this.$refs.pop.openPop();
    }
  }
}
</script>

<style>

</style>
