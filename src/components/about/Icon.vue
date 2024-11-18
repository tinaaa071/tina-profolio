<template>
    <div class="relative p-1 w-10 h-10 group">
      <!-- Image -->
      <img 
        :src="imageUrl" 
        alt="Example" 
        class="object-cover w-full h-full rounded"
      />
  
      <!-- Tooltip -->
      <div 
        class="absolute bottom-0 left-1/2 px-2 py-1 text-xs text-white rounded-md opacity-0 transition duration-300 transform -translate-x-1/2 translate-y-full bg-stone-900 group-hover:opacity-100 dark:bg-white dark:text-stone-900"
      >
        {{ tooltipText }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ImageWithTooltip',
    props: {
      imageUrl: {
        type: String,
        required: true,
      },
      tooltipText: {
        type: String,
        default: 'This is a tooltip',
      },
    },
  };
  </script>
  
  <style scoped>
  </style>
  