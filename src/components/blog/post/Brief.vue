<template>
  <div class="flex flex-col gap-6">
    <!-- Banner -->
    <div>
      <CardTilt>
        <img 
          class="object-cover object-center mb-2 w-full rounded-2xl sm:rounded-3xl aspect-video"
          :src="post.banner" 
          alt=""
        >
      </CardTilt>
      <p 
        v-if="showCredit"
        class="text-sm text-center text-stone-300 dark:text-stone-500">
        {{ post.credit }}
      </p>
    </div>
    <!-- Info -->
    <div>
      <!-- Category + Date -->
      <div class="flex gap-4 items-center mb-8 font-medium">
        <RouterLink :to="{ path: '../blog', query: { category: post.category }}" 
        class="text-B1"
        >
        {{ post.category }}
      </RouterLink>
        <span class="w-0.5 h-6 bg-stone-200 dark:bg-stone-500"></span>
        <p class="text-stone-400 dark:text-stone-500">
          {{ post.date }}
        </p>
      </div>
      <!-- Title + Desc -->
      <div class="mb-8">
        <h1 class="mb-4 text-3xl font-bold">
          {{ post.title }}
        </h1>
        <p class="text-lg text-stone-500 dark:text-stone-400">
          {{ post.desc }}
        </p>
      </div>
      <!-- Brief -->
      <div class="relative">
        <Fa6SolidQuoteLeft class="absolute -top-3 left-3 text-2xl text-B2 dark:text-stone-300" />
        <Fa6SolidQuoteRight class="absolute right-3 -bottom-3 text-2xl text-B2 dark:text-stone-300" />
        <div class="p-6 leading-loose text-center rounded-lg xl:px-32 bg-B4 dark:bg-stone-700">
          <slot name="brief"></slot>
        </div>
      </div>
    </div>
    <!-- Divider -->
    <Dot />
    <!-- Menu -->
    <div 
      v-if="showMenu && post.menu && post.menu.length > 0"
      class="px-8 py-5 text-sm rounded-lg text-stone-500 bg-B4 dark:bg-stone-700 dark:text-stone-300">
      <p class="mb-2">
        💡 大綱
      </p>
      <ul class="grid gap-2 list-decimal list-inside">
        <li v-for="(item, index) in post.menu" :key="index">
          {{ item.menu }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    linkTo: {
      type: String,
      required: true,
    },  
    post: {
      type: Object,
      required: true,
    },
    showCredit: {
      type: Boolean,
      default: true,
    },
    showMenu: {
      type: Boolean,
      default: true,
    },
  },
};
</script>
