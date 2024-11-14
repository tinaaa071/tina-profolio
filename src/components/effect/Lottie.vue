<template>
    <div 
      ref="lottieContainer" 
      :class="['lottie-container', heightClass, widthClass]" 
      
    ></div>
  </template>
  
  <script>
  import lottie from 'lottie-web';
  
  export default {
    name: 'LottieAnimation',
    props: {
      // 動畫 JSON 路徑
      path: {
        type: String,
        required: true,
      },
      // 高度和寬度
      heightClass: {
        type: String,
        default: 'h-12', // 預設為 3rem (12 * 0.25rem)
      },
      // 寬度的 Tailwind 類別
      widthClass: {
        type: String,
        default: 'w-12', // 預設為 3rem (12 * 0.25rem)
      },
    },
    mounted() {
      this.animation = lottie.loadAnimation({
        container: this.$refs.lottieContainer,
        renderer: 'svg',
        loop: true,
        autoplay: true, 
        path: this.path,
      });
    },
    beforeDestroy() {
      // 在組件銷毀時銷毀動畫
      if (this.animation) {
        this.animation.destroy();
      }
    },
    
  };
  </script>
  
  <style scoped>
  /* 你可以根據需要添加一些樣式 */
  </style>
  