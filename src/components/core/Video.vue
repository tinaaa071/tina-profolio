<template>
    <div class="overflow-hidden relative w-full rounded-2xl border sm:rounded-3xl border-stone-200 dark:border-stone-500">
      <iframe 
        :src="`${videoSrc}?autoplay=1`" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen
        class="w-full aspect-video"></iframe>
    </div>
  </template>
  
  <script setup>
  defineProps({
    videoSrc: {
      type: String,
      required: true
    }
  })
  </script>
  
  <style scoped>
  /* 可选: 添加自定义样式 */
  </style>
  