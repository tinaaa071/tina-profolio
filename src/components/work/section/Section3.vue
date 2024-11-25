<!-- Other Section -->
<template>
  <Section class="flex flex-col">
    <div class="w-full xl:px-56 md:p-8" :class="isSticky ? 'px-0' : 'px-6'">
      <div class="grid grid-cols-1 gap-6 md:grid-cols-10" >
        <!-- Title -->
        <div
          ref="stickyTitle"
          :class="[
            'sticky top-0 text-xl md:text-sm font-semibold md:top-5 md:col-span-2 text-stone-900 md:text-B1 dark:text-white h-fit transition duration-300 z-10 text-center md:text-left ',
            isSticky
              ? 'w-full flex justify-center from-stone-300/60 text-B1 dark:text-white text-center py-4 backdrop-blur bg-gradient-to-b '
              : '',
          ]"
        >
          {{ title }}
        </div>
        <!-- Content 1 -->
        <div class="col-span-1 md:col-span-8" :class="isSticky ? 'px-6' : 'px-0'" >
          <slot name="content-1"></slot>
        </div>
      </div>
    </div>
    <!-- Content 2 -->
    <div class="relative mt-6" v-if="$slots['content-2']" >
      <slot name="content-2"></slot>
    </div>
    <!-- Content 3 -->
    <div class="mt-6" v-if="$slots['content-3']" >
      <slot name="content-3"></slot>
    </div>
  </Section>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue';

export default {
  props: {
    title: {
      type: String,
      required: true,
    },
  },
  setup() {
    const stickyTitle = ref(null);
    const isSticky = ref(false);

    const handleScroll = () => {
      if (stickyTitle.value) {
        // Check if the element is at the top of the viewport
        const { top } = stickyTitle.value.getBoundingClientRect();
        isSticky.value = top <= 0; // Adjust condition as needed
      }
    };

    onMounted(() => {
      window.addEventListener('scroll', handleScroll);
    });

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll);
    });

    return { stickyTitle, isSticky };
  },
};
</script>
