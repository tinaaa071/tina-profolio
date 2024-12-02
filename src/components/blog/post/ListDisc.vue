<template>
    <ul class="leading-loose list-disc list-inside">
      <li v-for="(item, index) in items" :key="index">
        <span class="font-semibold">
          {{ item.title }}
        </span>
        <br>
        <span class="block ml-5">
          {{ item.description }}
        </span>
      </li>
    </ul>
  </template>
  
  <script setup>
  defineProps({
    items: {
      type: Array,
      required: true,
      default: () => [],
    },
  });
  </script>
  