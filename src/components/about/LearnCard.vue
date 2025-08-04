<template>
  <div 
  class="relative w-full overflow-hidden font-semibold border shadow h-44 rounded-2xl sm:rounded-3xl aspect-video group border-B4 text-stone-800 dark:border-white dark:text-white"
  >
    <!-- Title -->
    <!-- <div class="absolute backdrop-blur-md bg-stone-900/10">
      <div class="p-4">
        <p class="mb-2 text-white dark:text-stone-800 group-hover:hidden">
          {{ title }}
        </p>
      </div>
    </div> -->
    <!-- Hidden 區塊 -->
    <div class="absolute w-full p-4 transition-all duration-300 ease-in-out bg-white shadow-md -top-32 dark:bg-stone-900 group-hover:top-0">
    <p class="mb-1">
        {{ title }}
    </p>
    <!-- <p class="text-sm text-stone-400">
        {{ info }}
    </p> -->
    </div>
    <!-- Img -->
    <div class="h-full mt-0 transition-all duration-300 ease-in-out group-hover:mt-16">
      <img 
      class="object-cover w-full h-full"
      :src="cardSrc" 
      alt="">
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    info: {
      type: String,
      required: true,
    },
    cardSrc: {
      type: String,
      default: '',
    },
  }
};
</script>