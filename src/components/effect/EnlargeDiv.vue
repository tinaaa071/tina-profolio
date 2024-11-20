<template>
    <!-- 外框 -->
    <div
      ref="container"
      class="overflow-hidden relative h-64 rounded-2xl transition-all xl:rounded-3xl"
      style="width: 50%"
    >
      <div
        ref="zoomElement"
        class="w-full h-full bg-center bg-cover"
        :style="{ backgroundImage: 'url(' + imageUrl + ')' }"
      ></div>
    </div>
  </template>
  
  <script setup>
  import { onMounted, ref, defineProps } from 'vue'
  import gsap from 'gsap'
  import ScrollTrigger from 'gsap/ScrollTrigger'
  
  // 接收父组件传递的 imageUrl
  const props = defineProps({
    imageUrl: {
      type: String,
      required: true,
    },
  })
  
  const container = ref(null)
  const zoomElement = ref(null)
  
  onMounted(() => {
    gsap.registerPlugin(ScrollTrigger)
  
    // 创建 ScrollTrigger 监听器
    ScrollTrigger.create({
      trigger: zoomElement.value,
      start: 'top 80%', // 元素进入视口时
      end: 'bottom 30%', // 完整的滚动范围
      scrub: true, // 启用平滑滚动
      onUpdate: ({ progress }) => {
        // 根据滚动进度动态改变外框宽度
        const newWidth = progress < 1 ? `${80 + (progress * 20)}%` : '100%' // 动态变化宽度
        gsap.to(container.value, { width: newWidth })
      },
      onLeave: () => {
        // 滚动离开时确保宽度设置为 w-full
        gsap.to(container.value, { width: '100%' })
      },
      onEnterBack: () => {
        // 返回到该区域时，确保宽度再次设置为 w-full
        gsap.to(container.value, { width: '100%' })
      }
    })
  
    // 设置元素缩放动画
    gsap.fromTo(
      zoomElement.value,
      { scale: 1 },
      {
        scale: 1.5, // 最大放大比例
        scrollTrigger: {
          trigger: zoomElement.value,
          start: 'top 80%',
          end: 'bottom 30%',
          scrub: true,
        },
      }
    )
  })
  </script>
  
  <style scoped>
  /* 确保元素填充容器 */
  div {
    position: relative;
  }
  
  div > div {
    transition: transform 0.2s ease;
  }
  </style>
  