<template>
  <div
    class="relative w-full bg-cover"
    :class="[
      customClass,
      { 
        'bg-cover bg-no-repeat': isMobile,  // 手機版使用 bg-cover
        'bg-fixed': !isMobile,  // 非手機版才顯示 parallax 視差效果
      }
    ]"
    :style="{
      backgroundImage: `url(${backgroundImage})`,
      backgroundPosition: isMobile ? 'center' : `center ${offsetY}px`, // 只在桌機版顯示視差效果
    }"
  >
    <div class="absolute inset-0 flex items-center justify-center text-2xl">
      <slot>{{ text }}</slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "ParallaxSection",
  props: {
    backgroundImage: {
      type: String,
      required: true,
    },
    speed: {
      type: Number,
      default: 0.5, // 控制視差速度
    },
    text: {
      type: String,
      default: "",
    },
    customClass: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      offsetY: 0,
      isMobile: window.innerWidth <= 768, // 偵測螢幕是否為手機版
    };
  },
  methods: {
    handleScroll() {
      if (!this.isMobile) {
        const rect = this.$el.getBoundingClientRect();
        if (rect.top <= window.innerHeight && rect.bottom >= 0) {
          this.offsetY = rect.top * this.speed;
        }
      }
    },
    handleResize() {
      this.isMobile = window.innerWidth <= 768; // 偵測螢幕尺寸
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
    window.addEventListener("resize", this.handleResize); // 監聽視窗大小變動
    this.handleScroll(); // 初始化滾動
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
    window.removeEventListener("resize", this.handleResize); // 移除監聽器
  },
};
</script>
