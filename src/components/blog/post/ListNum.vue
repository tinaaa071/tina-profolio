<template>
  <ol :class="['leading-loose list-decimal list-inside', customClass]">
    <li 
      v-for="(item, index) in items" 
      :key="index"
    >
      <template v-if="showNote && item.title">
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
      <!-- 這裡確保無論換行與否，description 保持一致的縮排 -->
      <span 
      v-html="item.description"
      :class="!item.title ? '' : 'ml-3 md:ml-5 block'"
      >
      </span>
      <div class="ml-3 md:ml-5">
        <slot :name="'slot-' + index"></slot>
      </div>
    </li>
  </ol>
</template>

<script setup>
defineProps({
  items: {
    type: Array,
    required: true,
    default: () => [],
  },
  showNote: {
    type: Boolean,
    default: true,
  },
  customClass: {
    type: String,
    default: '', // 默認為空字符串，無附加類別
  },
});
</script>
