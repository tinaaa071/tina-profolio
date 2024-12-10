<template>
    <div class="relative">
      <iframe 
        :src="`${videoSrc}?autoplay=1`" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen
        class="w-full"
        :class="videoClass"
        >
      </iframe>
    </div>
  </template>
  
  <script setup>
  defineProps({
    videoSrc: {
      type: String,
      required: true
    },
    videoClass: {
      type: Array,
      default: 'aspect-video'
    }
  })
  </script>
  
  <style scoped>
  /* 可选: 添加自定义样式 */
  </style>
  