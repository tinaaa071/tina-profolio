<template>
    <div>
        <img 
        class="object-cover object-center mb-1 rounded-2xl border sm:mb-2 sm:rounded-3xl aspect-video border-stone-200 dark:border-stone-500"
        :src="imgSrc"
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
      }
    },
  };
  </script>