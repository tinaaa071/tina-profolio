<template>
  <p 
    v-if="link" 
    class="text-lg font-bold underline md:text-xl">
    <a :href="link" target="_blank" rel="noopener noreferrer">
      {{ title }}
    </a>
  </p>
  <p 
    v-else 
    class="text-lg font-bold md:text-xl">
    {{ title }}
  </p>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: ''
    },
    link: {
      type: String,
      default: ''
    }
  }
};
</script>
