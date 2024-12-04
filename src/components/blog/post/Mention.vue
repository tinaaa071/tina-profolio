<template>
  <div>
      <p v-if="showNote" class="mb-2">
          {{ note }}
      </p>
      <!-- 使用條件渲染來正確選擇 RouterLink 或 a -->
      <template v-if="isExternal">
          <a
              :href="link"
              target="_blank"
              rel="noopener noreferrer"
              class="flex gap-3 p-2 rounded-2xl border transition-colors sm:p-3 sm:gap-6 border-stone-300 group hover:border-stone-400 dark:border-stone-400 dark:hover:border-white"
          >
          <div class="py-2 w-full">
                <p class="mb-2 font-semibold">
                    {{ title }}
                </p>
                <p class="text-sm line-clamp-2">
                    {{ content }}
                </p>
            </div>
            <div class="overflow-hidden w-28 rounded-2xl border border-stone-200 aspect-square">
                <img 
                    :src="image" 
                    alt="image"
                    class="object-cover object-center w-full h-full transition-transform group-hover:scale-125"
                >
            </div>
          </a>
      </template>
      <template v-else>
          <RouterLink
              :to="link"
              class="flex gap-3 p-2 rounded-2xl border transition-colors sm:p-3 sm:gap-6 border-stone-300 group hover:border-stone-400 dark:border-stone-400 dark:hover:border-white"
          >
          <div class="py-2 w-full">
                <p class="mb-2 font-semibold">
                    {{ title }}
                </p>
                <p class="text-sm line-clamp-2">
                    {{ content }}
                </p>
            </div>
            <div class="overflow-hidden w-28 rounded-2xl border border-stone-200 aspect-square">
                <img 
                    :src="image" 
                    alt="image"
                    class="object-cover object-center w-full h-full transition-transform group-hover:scale-125"
                >
            </div>
          </RouterLink>
      </template>
  </div>
</template>

<script setup>
defineProps({
  showNote: {
    type: Boolean,
    required: true
  },
  link: {
    type: String,
    required: true
  },
  isExternal: {
    type: Boolean,
    required: false,
    default: false
  },
  title: {
    type: String,
    required: true
  },
  note: {
    type: String,
    required: false,
    default: '📌\u00A0\u00A0也可以參考下面這篇分享：'
  },
  content: {
    type: String,
    required: true
  },
  image: {
    type: String,
    required: true
  }
})
</script>
