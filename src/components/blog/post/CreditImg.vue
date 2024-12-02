<template>
    <div>
        <img 
        class="object-cover object-center mb-2 w-full rounded-2xl sm:rounded-3xl aspect-video"
        :src="imgSrc"
        >
        <p 
            class="text-sm text-center text-stone-300 dark:text-stone-500">
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