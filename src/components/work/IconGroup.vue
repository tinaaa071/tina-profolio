<!-- src/components/IconGroup.vue -->
<template>
    <div class="flex flex-col justify-items-center items-center space-y-4 text-2xl text-white sm:space-y-5">
        <fa6-solid-envelope v-if="iconsVisible[0]" aria-hidden="true" />
        <fa6-solid-apple-whole v-if="iconsVisible[1]"  aria-hidden="true" />
        <Icon 
        imageUrl="https://images.unsplash.com/photo-1725714834412-7d7154ac4e4e?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
        tooltipText="image"
        v-if="iconsVisible[2]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://images.unsplash.com/photo-1725714834412-7d7154ac4e4e?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
        tooltipText="image"
        v-if="iconsVisible[3]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://images.unsplash.com/photo-1725714834412-7d7154ac4e4e?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
        tooltipText="image"
        v-if="iconsVisible[4]"  aria-hidden="true" 
        />
    </div>
  </template>
  
  <script>
  export default {
    name: "IconGroup",
    props: {
      iconsVisible: {
        type: Array,
        default: () => [false, false, false, false, false], // Default to all hidden
        validator: (value) => value.length === 5 && value.every((item) => typeof item === 'boolean'),
      },
    },
  };
  </script>
