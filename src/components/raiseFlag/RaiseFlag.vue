<template>
  <div>
  <!-- 版本一 -->
   <!-- <div v-show="activePhoto === 0">
      <div class="btn-raise" @click="raise">升旗</div>
      <img src="../../assets/img/down.jpg" alt="" style="width: 100%;">
    </div>
    <div v-show="activePhoto === 1">
      <img src="../../assets/img/动9.gif" style="width: 100%;">
      <a href="" class="btn-luck-draw" v-if="activeBtn" :style="{'box-shadow': '0 0 15px ' + shadowsAdjust + 'px' + ' rgb(216, 36, 37)'}">抽奖</a>
    </div> -->

  <!-- 版本二 -->
  <!-- 顶部的bar -->
    <div class="top-bar">
      <!-- 升旗与抽奖按钮 -->
      <div class="btn-public btn-raise" @click="raise" v-show="activePhoto === 0">升旗</div>
      <div class="btn-public " v-show="activePhoto === 1"></div>
      <!-- <div class="btn-public btn-raise" v-show="activePhoto === 2">抽奖</div> -->
      <a href="" class="btn-public btn-raise" v-show="activePhoto === 2">抽奖</a>
    </div>
    <!-- 升国旗前的静态图 -->
    <div v-show="activePhoto === 0"><img src="../../assets/img/2ef32bd57f5d7ea709c7cbbdfe0d042.jpg" style="width: 100%;"></div>
    <!-- 升国旗的动图 -->
    <div v-show="activePhoto === 1 || activePhoto === 2"><img src="../../assets/img/动10.gif" style="width: 100%;"></div>
  </div>

</template>

<script>
export default {
  name: 'Raise',
  data () {
    return {
      // 控制图片的切换展示
      activePhoto: 0,
      // 控制抽奖按钮的出现
      activeBtn: false,
      // 控制抽奖按钮的动画
      shadowsAdjust: 0,
      // 控制阴影的缩放
      cycle: true
    }
  },
  methods: {
    // 点击升旗
    raise () {
      this.activePhoto = 1
      setTimeout(() => {
        // this.activeBtn = true
        // setInterval(() => {
        //   if (this.cycle) {
        //     this.shadowsAdjust++
        //     if (this.shadowsAdjust % 7 === 0) {
        //       this.cycle = !this.cycle
        //     }
        //   } else {
        //     this.shadowsAdjust--
        //     if (this.shadowsAdjust === 0) {
        //       this.cycle = !this.cycle
        //     }
        //   }
        // }, 75)
        this.activePhoto = 2
      }, 3500)
    }
  }
}
</script>

<style>
  .top-bar {
    position: relative;
    width: 100%;
    height: 40px;
    background-color: rgb(216, 36, 37);
  }
  .btn-public {
    position: absolute;
    top: 20px;
    right: 50%;
    margin-right: -20px;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background-color: rgb(247, 192, 185);
    border: 3px solid rgb(247, 192, 185);
    box-shadow: 0 0 0 5px rgb(216, 36, 37);
  }
  .btn-raise {
    line-height: 40px;
    text-align: center;
    color: rgb(247, 192, 185);
    background-color: rgb(216, 36, 37) !important;
  }

  .btn-luck-draw {
    position: absolute;
    top: 40%;
    right: 35%;
    width: 40px;
    height: 40px;
    line-height: 40px;
    text-align: center;
    border-radius: 50%;
    color: rgb(247, 192, 185);
    background-color: rgb(216, 36, 37);
    border: 3px solid rgb(247, 192, 185);
    text-decoration: none;
  }
</style>
