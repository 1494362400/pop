<template>
  <div id="pop" v-if="popFlag">
    <div class="popBox">
      <div class="header">
        <p class="title">{{ popData.title }}</p>
        <button class="close" @click="closePop()">x</button>
      </div>
      <div class="content">
        <p>
          {{ popData.content }}
        </p>
      </div>
      <div class="footer">
        <div class="btnGroup">
          <input
            type="button"
            v-if="popData.cancleBtn"
            :value="popData.cancleBtn"
            @click="closePop()"
            class="cancle"
          />
          <input
            type="button"
            :value="popData.confirmBtn"
            @click="confirmPop()"
            class="confirm"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    popData: {
      type: Object,
      default() {
        return {
          title: "提示",
          content: "此操作将永久删除文件，是否继续？",
          cancleBtn: "取消",
          confirmBtn: "确定",
        };
      },
    },
  },
  data() {
    return {
      popFlag: false,
    };
  },
  methods: {
    openPop() {
      this.popFlag = true;
    },
    closePop() {
      this.popFlag = false;
    },
    confirmPop() {
      this.popFlag = false;
    },
  },
};
</script>
<style lang="less" scoped>
#pop {
  position: absolute;
  background: rgba(0, 0, 0, 0.2);
  width: 100%;
  height: 100vh;
  top: 0;
  left: 0;
}
.popBox {
  position: absolute;
  left: calc(50% - 250px);
  top: calc(50% - 200px);
  background: #fff;
  width: 500px;
  height: 200px;
  vertical-align: middle;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  .header {
    display: flex;
    justify-content: space-between;
    margin: 0 auto;
    width: 450px;
    .title {
      font-size: 20px;
    }
    .close {
      border: none;
      background: none;
      font-size: 16px;
    }
  }
  .content {
    margin: 0 auto;
    width: 450px;
    display: flex;
  }
  .footer {
    margin: 0 auto;
    width: 450px;
    display: flex;
    .btnGroup {
      margin-left: 300px;
      input {
        border: none;
        border-radius: 5px;
        width: 80px;
        height: 40px;
      }
      .cancle {
        background: #f8f8f8;
      }
      .confirm {
        background: rgb(32, 169, 233);
        margin-left: 20px;
      }
    }
  }
}
</style>