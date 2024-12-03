<template>
    <div>
        <p v-if="showTitle" class="mb-2">
            📌 也可以參考下面這篇分享：
        </p>
        <RouterLink :to="link" class="flex gap-3 p-3 rounded-2xl border transition-colors sm:gap-6 border-stone-300 group hover:border-stone-400 dark:border-stone-400 dark:hover:border-white">
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
    </div>
</template>

<script setup>
defineProps({
  showTitle: {
    type: Boolean,
    required: true
  },
  link: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
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
