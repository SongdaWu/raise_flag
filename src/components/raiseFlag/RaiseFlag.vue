<template>
  <div>
    <div v-show="activePhoto === 0">
      <div class="btn-raise" @click="raise">升旗</div>
      <img src="../../assets/img/down.jpg" alt="" style="width: 100%;">
    </div>
    <div v-show="activePhoto === 1">
      <img src="../../assets/img/动9.gif" style="width: 100%;">
      <a href="" class="btn-luck-draw" v-if="activeBtn" :style="{'box-shadow': '0 0 5px ' + shadowsAdjust + 'px' + ' rgb(216, 36, 37)'}">抽奖</a>
    </div>
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
      i: true
      // styles: {
      //   'box-shadow': {
      //     'h-shadow': '0',
      //     'v-shadow': '0',
      //     blur: '5px',
      //     spread: this.shadowsAdjust + 'px',
      //     color: 'rgb(216, 36, 37)'
      //   }
      // ['0', '0', '5px', this.shadowsAdjust + 'px', 'rgb(216, 36, 37)']
      // 0 0 5+'px' shadowsAdjust+'px' 'rgb(216, 36, 37)
      // }
    }
  },
  methods: {
    raise () {
      this.activePhoto = 1
      setTimeout(() => {
        this.activeBtn = true
        this.lll()
      }, 3500)
    },
    lll () {
      setInterval(() => {
        if (this.i) {
          this.shadowsAdjust++
          if (this.shadowsAdjust % 5 === 0) {
            this.i = !this.i
            console.log(this.i)
            console.log(typeof (i))
          }
        } else {
          this.shadowsAdjust--
          if (this.shadowsAdjust % 5 === 0) {
            this.i = !this.i
            console.log(this.i)
          }
        }
      }, 300)
    }
  }
}

</script>

<style>
  .btn-raise {
    position: absolute;
    top: 30%;
    right: 40%;
    width: 40px;
    height: 40px;
    line-height: 40px;
    text-align: center;
    border-radius: 50%;
    color: rgb(247, 192, 185);
    background-color: rgb(216, 36, 37);
    border:3px solid rgb(247, 192, 185);
    box-shadow: 0 0 5px 5px rgb(216, 36, 37);
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
    border:3px solid rgb(247, 192, 185);
    text-decoration: none;
  }
</style>
