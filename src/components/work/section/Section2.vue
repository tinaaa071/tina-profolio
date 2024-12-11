<template>
  <Section
    class="flex flex-col gap-6 text-center md:gap-8 xl:px-56 md:p-8"
    :class="isSticky ? 'px-0' : 'px-6'"
  >
    <!-- Title -->
    <p
      ref="stickyTitle"
      :class="[
        'sticky top-0 text-lg md:text-3xl font-semibold text-stone-900 md:text-B1 dark:text-white h-fit transition duration-300 z-10 md:static',
        {
          'w-full flex justify-center from-stone-300/60 text-B1 dark:text-white text-center py-4 backdrop-blur bg-gradient-to-b':
            isSticky,
        },
      ]"
    >
      {{ $t('work.title.item2') }}
    </p>
    <!-- Grid -->
    <div
      class="grid gap-2 text-left sm:gap-3 sm:grid-cols-2"
      :class="{ 'px-6': isSticky, 'px-0': !isSticky }"
    >
      <div
        v-for="(brief, index) in briefs"
        :key="index"
        class="p-4 text-justify rounded-2xl border transition-colors duration-75 sm:rounded-lg sm:p-6 border-stone-200 hover:bg-stone-50 dark:hover:bg-stone-800"
      >
        <p class="mb-2 font-semibold">
          {{ `${(index + 1).toString().padStart(2, '0')} ` }}&ensp;|&ensp;
          <span>
            {{ $t(brief.title) }}
          </span>
        </p>
        <p class="font-normal text-stone-700 dark:text-stone-300">
          {{ $t(brief.content) }}
        </p>
      </div>
    </div>
  </Section>
</template>

<script>
import { ref, onMounted, onUnmounted, computed } from 'vue';

export default {
  props: {
    briefs: {
      type: Array,
      required: true,
    },
  },
  setup() {
    const stickyTitle = ref(null);
    const isSticky = ref(false);
    const isSmallScreen = ref(true);

    const handleScroll = () => {
      if (stickyTitle.value && isSmallScreen.value) {
        const { top } = stickyTitle.value.getBoundingClientRect();
        isSticky.value = top <= 0;
      }
    };

    const handleResize = () => {
      isSmallScreen.value = !window.matchMedia('(min-width: 768px)').matches; // 'sm' breakpoint
      if (!isSmallScreen.value) {
        isSticky.value = false; // 禁用 sticky 行為
      }
    };

    onMounted(() => {
      window.addEventListener('scroll', handleScroll);
      window.addEventListener('resize', handleResize);
      handleResize(); // 初始化
    });

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll);
      window.removeEventListener('resize', handleResize);
    });

    return { stickyTitle, isSticky };
  },
};
</script>
