<template>
    <div 
      :style="{ backgroundImage: `url(${backgrounds[activeTab - 1]})` }"
      class="flex overflow-hidden flex-col p-4 bg-center bg-no-repeat bg-cover rounded-2xl border cursor-default sm:p-6 dark:border-white border-B4 text-stone-900 dark:text-white sm:rounded-3xl h-fit dark:bg-transparent"
    >
      <!-- Top Section -->
      <div class="flex gap-12 items-center p-3 mb-6 font-semibold bg-white rounded-lg xl:mb-10 sm:px-8 sm:rounded-xl dark:bg-stone-900">
        <button
          v-for="(button, index) in buttons"
          :key="index"
          type="button"
          class="inline-flex justify-center w-full leading-normal text-center transition-colors duration-300 ease-in-out sm:text-base"
          :class="{
            'text-stone-900 dark:text-white': activeTab === index + 1,
            'text-stone-400 hover:text-stone-900 dark:text-stone-500 dark:hover:text-white': activeTab !== index + 1
          }"
          @click="selectTab(index + 1)"
        >
          {{ $t(button) }}
        </button>
      </div>
  
      <!-- Bottom Section -->
      <div 
      class="text-sm font-normal rounded-xl sm:text-base"
      :class="customClass"
      >
        <SkeletonLoader v-if="loading" size="full" />
        <TabTransition v-else>
          <slot :active-tab="activeTab" />
        </TabTransition>
      </div>
    </div>
  </template>
  
  <script>
  import { ref, onMounted } from 'vue';
  
  export default {
    props: {
      buttons: {
        type: Array,
        required: true,
      },
      customClass: {
        type: Array,
        default: 'p-3 sm:p-4 backdrop-blur-sm bg-white/60 dark:bg-stone-900/40',
      },
    },
    setup(_, { slots }) {
      const loading = ref(true);
      const activeTab = ref(1);
  
      const backgrounds = ref(
        slots.backgrounds ? slots.backgrounds().map((vnode) => vnode.props?.src) : []
      );
  
      const selectTab = (tab) => {
        activeTab.value = tab;
      };
  
      onMounted(() => {
        setTimeout(() => {
          loading.value = false;
        }, 2000);
      });
  
      return {
        loading,
        activeTab,
        selectTab,
        backgrounds,
      };
    },
  };
  </script>
  