<template>
  <p 
    v-if="link" 
    class="pl-4 text-xl font-bold underline border-l-4 border-amber-200 md:text-2xl">
    <a :href="link" target="_blank" rel="noopener noreferrer">{{ title }}</a>
  </p>
  <p 
    v-else 
    class="pl-4 text-xl font-bold border-l-4 border-amber-200 md:text-2xl">
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
