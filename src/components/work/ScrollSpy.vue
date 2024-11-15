<template>
  <nav class="hidden sticky top-0 left-0 z-50 xl:block">
    <div class="absolute pt-5 ml-6 text-xs w-fit">
      <ul class="p-0 list-none">
        <li
          v-for="section in sections"
          :key="section.id"
          :class="[
            'my-3 relative',
            activeSection === section.id ? 'text-B1 font-bold dark:text-white pl-4' : 'text-stone-300 dark:text-stone-400',
            'transition-all duration-300'  // 添加過渡效果
          ]"
        >
          <a
            :href="'#' + section.id"
            class="no-underline transition-colors hover:text-stone-400 before:content-[''] before:absolute before:left-0 before:top-1/2 before:translate-y-[-50%] before:h-0.5 before:w-2 before:bg-current"
            :class="{
              'before:opacity-100': activeSection === section.id,  // active 狀態顯示橫條
              'before:opacity-0': activeSection !== section.id      // 非 active 狀態隱藏橫條
            }"
            @click.prevent="smoothScroll(section.id)"
          >
            {{ $t(section.name) }}
          </a>
        </li>
    </ul>
    </div>
  </nav>
</template>

<script>
import { onMounted, onBeforeUnmount, ref } from 'vue';

export default {
  props: {
    sections: {
      type: Array,
      required: true,
    },
  },
  setup(props) {
    const activeSection = ref('');

    const onScroll = () => {
      let currentSection = '';
      props.sections.forEach((section) => {
        const element = document.getElementById(section.id);
        if (
          element &&
          element.getBoundingClientRect().top <= window.innerHeight / 2 &&
          element.getBoundingClientRect().bottom > window.innerHeight / 2
        ) {
          currentSection = section.id;
        }
      });
      activeSection.value = currentSection;
    };

    const smoothScroll = (id) => {  // 新增的平滑滾動函數
      const element = document.getElementById(id);
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
      }
    };

    // Throttle the scroll event handler
    const throttledOnScroll = throttle(onScroll, 100);

    onMounted(() => {
      window.addEventListener('scroll', throttledOnScroll);
      throttledOnScroll(); // Initial check to set the active section
    });

    onBeforeUnmount(() => {
      window.removeEventListener('scroll', throttledOnScroll);
    });

    return {
      activeSection,
      smoothScroll
    };
  },
};

// Helper function to throttle scroll events
function throttle(func, delay) {
  let lastCall = 0;
  return function (...args) {
    const now = new Date().getTime();
    if (now - lastCall < delay) {
      return;
    }
    lastCall = now;
    return func(...args);
  };
}
</script>