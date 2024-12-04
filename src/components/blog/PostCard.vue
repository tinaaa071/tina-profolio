<template>
    <RouterLink :to="linkTo" >
      <!-- img -->
      <div class="group">
        <div
        :class="[
          'overflow-hidden relative w-full border dark:border-white/20 border-stone-200',
          aspectRatioClass,
        ]"
      >
      <div
          v-if="showTag"
          class="flex absolute right-4 bottom-4 z-10 flex-wrap gap-2"
        >
          <!-- 判斷 category 是陣列還是單一值 -->
          <template v-if="Array.isArray(post.category)">
            <span
              v-for="(category, index) in post.category"
              :key="index"
              class="px-1.5 py-1 text-xs font-normal whitespace-nowrap rounded bg-stone-50 text-stone-600"
            >
              {{ category }}
            </span>
          </template>
          <template v-else>
            <span
              class="px-1.5 py-1 text-xs font-normal whitespace-nowrap rounded bg-stone-50 text-stone-600"
            >
              {{ post.category }}
            </span>
          </template>
        </div>
        <img 
        :src="post.image" 
        :alt="post.title" 
        class="object-cover object-center w-full h-full transition-all duration-300 ease-in-out group-hover:scale-110"
        />
      </div>
      
      <p 
      v-if="showDate"
      class="px-2 py-2 text-xs font-normal tracking-widest border-b md:py-3 xl:px-4 border-stone-200 dark:border-stone-500 text-stone-500 dark:text-stone-400"
      >
        {{ post.date }}
      </p>
      <p class="px-2 py-2 text-base font-medium text-justify md:text-sm xl:text-base xl:px-4 line-clamp-3 dark:text-white">
        {{ post.title }}
      </p>
      </div>
    </RouterLink>
  </template>
  
  <script>
  export default {
    name: "PostItem",
    props: {
      linkTo: {
        type: String,
        required: true,
      },  
      post: {
        type: Object,
        required: true,
      },
      showTag: {
        type: Boolean,
        required: true,
      },
      showDate: {
        type: Boolean,
        required: true,
      },
      aspectRatio: {
      type: String,
      default: "aspect-video rounded-lg ", // 預設值為 'aspect-video'
      },
    },
    computed: {
      aspectRatioClass() {
        return this.aspectRatio;
      },
    },
  };
  </script>