<template>
    <div>
      <img 
        class="object-cover object-center mb-1 w-full rounded-2xl border sm:mb-2 sm:rounded-3xl border-stone-200 dark:border-stone-500"
        :src="imgSrc"
        :class="aspectRatio"
      >
        <p 
            class="text-xs text-center sm:text-sm text-stone-300 dark:text-stone-500">
            {{ imgCredit }}
        </p>
    </div>
</template>
  
<script>
  export default {
    props: {
      imgSrc: {
        type: String,
        required: true,
      },  
      imgCredit: {
        type: String,
        required: false,
      },
      aspectRatio: {
        type: String,
        default: 'aspect-video', // 默認比例為 16:9
      },
    },
  };
  </script>