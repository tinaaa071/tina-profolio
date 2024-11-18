<template>
    <div
      class="overflow-hidden relative w-full bg-fixed bg-no-repeat bg-cover"
      :class="customClass"
      :style="{
        backgroundImage: `url(${backgroundImage})`,
        backgroundPosition: `center ${offsetY}px`,
      }"
    >
      <div class="flex absolute inset-0 justify-center items-center text-2xl">
        <slot>{{text}}</slot>
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
        default: ''
      },
      customClass: {
        type: String,
        default: "",
      },
    },
    data() {
      return {
        offsetY: 0,
      };
    },
    methods: {
      handleScroll() {
        const rect = this.$el.getBoundingClientRect();
        if (rect.top <= window.innerHeight && rect.bottom >= 0) {
          this.offsetY = rect.top * this.speed;
        }
      },
    },
    mounted() {
      window.addEventListener("scroll", this.handleScroll);
      this.handleScroll(); // 初始化滾動
    },
    beforeUnmount() {
      window.removeEventListener("scroll", this.handleScroll);
    },
  };
  </script>
  