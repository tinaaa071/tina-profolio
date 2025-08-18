<template>
  <div>
    <!-- 如果網站關閉，顯示關閉頁面 -->
    <ClosedPage v-if="!siteEnabled" />
    
    <!-- 如果網站開啟，正常使用 RouterView -->
    <RouterView v-else />
  </div>
</template>

<script setup>
import ClosedPage from './components/core/ClosedPage.vue'

// 根據 .env 設定判斷網站是否開啟
const siteEnabled = import.meta.env.VITE_SITE_ENABLED === 'true'
</script>
