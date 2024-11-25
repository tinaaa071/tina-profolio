<template>
    <section
      :id="id"
      class="flex justify-center py-8 bg-white cursor-default xl:py-8 dark:bg-stone-900"
    >
      <slot></slot>
    </section>
  </template>
  
  <script>
  export default {
    props: {
      id: {
        type: String,
        required: true,
      },
      title: {
        type: String,
        required: true,
      },
      content: {
        type: String,
        required: true,
      },
    },
  };
  </script>

  