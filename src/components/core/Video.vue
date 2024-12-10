<template>
    <div 
    :class="customClass">
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
    customClass: {
      type: Array,
      default: 'overflow-hidden relative w-full '
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
  