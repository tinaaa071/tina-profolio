<template>
  <ul :class="['leading-loose list-disc list-inside', customClass]">
    <li v-for="(item, index) in items" :key="index">
      <template v-if="showTitle && item.title">
        <span class="font-semibold">
          <template v-if="item.link">
            <a :href="item.link" target="_blank" rel="noopener noreferrer" class="underline">
              {{ item.title }}
            </a>
          </template>
          <template v-else>
            {{ item.title }}
          </template>
        </span>
        <br>
      </template>
      <span 
      v-html="item.description"
      :class="!item.title ? '' : 'ml-5 block'"
      >
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
  showTitle: {
    type: Boolean,
    default: true,
  },
  customClass: {
    type: String,
    default: '', // 默認為空字符串，無附加類別
  },
});
</script>
