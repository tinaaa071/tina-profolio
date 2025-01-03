<template>
  <div class="relative">
    <div v-if="isVideoUrl(videoSrc)">
      <!-- 使用 <video> 顯示影片，並加入 loop 和 muted 屬性 -->
      <video 
        :src="videoSrc" 
        autoplay 
        controls
        loop
        muted
        class="w-full"
        :class="videoClass"
      ></video>
    </div>
    <div v-else>
      <!-- 如果是非影片 URL，則顯示嵌入影片 -->
      <iframe 
        :src="`${videoSrc}?autoplay=1&loop=1&mute=1`" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen
        class="w-full"
        :class="videoClass"
      ></iframe>
    </div>
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
    default: () => ['aspect-video']
  }
})

const isVideoUrl = (url) => {
  const videoFormats = ['mp4', 'webm', 'ogg']; // 支援的影片格式
  return videoFormats.some(format => url.endsWith(format));
}
</script>

<style scoped>
/* 可选: 添加自定义样式 */
</style>
