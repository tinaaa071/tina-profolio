<template>
    <div class="flex flex-col gap-3">
      <!-- 使用 v-for 渲染卡片 -->
      <div
        v-for="(card, index) in cards"
        :key="index"
        class="flex flex-row gap-4 items-center p-4 w-full rounded-2xl border border-stone-800/20 dark:border-stone-200"
      >
        <img
          :src="card.avatarSrc"
          alt="Avatar"
          class="object-cover mb-2 w-16 rounded-2xl aspect-square"
        />
        <div>
            <p class="mb-2 font-semibold">
                {{ card.title }}
            </p>
            <p>
                {{ card.content }}
            </p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      cards: {
        type: Array,
        required: true,
      },
    },
  };
  </script>
  