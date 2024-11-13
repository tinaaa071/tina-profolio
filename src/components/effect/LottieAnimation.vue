<template>
    <div 
      ref="lottieContainer" 
      :style="{ height: height, width: width }" 
      @mouseover="playAnimation" 
      @mouseleave="stopAnimation"
    ></div>
  </template>
  
  <script>
  import lottie from 'lottie-web';
  
  export default {
    name: 'LottieAnimation',
    props: {
      // 動畫 JSON 路徑
      animationData: {
        type: Object,
        required: true,
      },
      // 高度和寬度
      height: {
        type: String,
        default: '100px',
      },
      width: {
        type: String,
        default: '100px',
      },
    },
    mounted() {
      // 初始化 Lottie 動畫，但預設顯示在最後一幀
      this.animation = lottie.loadAnimation({
        container: this.$refs.lottieContainer,
        renderer: 'svg',
        loop: true,
        autoplay: false, // 不自動播放，會保持在最後一幀
        animationData: this.animationData,
      });
  
      // 跳轉到動畫的最後一幀
      this.animation.goToAndStop(this.animation.totalFrames - 1, true);
    },
    beforeDestroy() {
      // 在組件銷毀時銷毀動畫
      if (this.animation) {
        this.animation.destroy();
      }
    },
    methods: {
      // 當鼠標懸停時播放動畫
      playAnimation() {
        if (this.animation) {
          this.animation.play();
        }
      },
      // 當鼠標移開時停止動畫並回到最後一幀
      stopAnimation() {
        if (this.animation) {
          this.animation.stop();
          // 當停止動畫後，回到最後一幀
          this.animation.goToAndStop(this.animation.totalFrames - 1, true);
        }
      },
    },
  };
  </script>
  
  <style scoped>
  /* 你可以根據需要添加一些樣式 */
  </style>
  