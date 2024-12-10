<template>
    <div class="w-[200px] relative z-50">
        <div
        class="flex overflow-hidden absolute bottom-0 flex-col gap-3 p-3 px-3.5 text-left rounded-3xl shadow-lg transition-all duration-200 ease-in-out cursor-pointer bg-stone-800 dark:bg-stone-300 hover:p-3.5 w-fit"
        :class="customClass"
        @mouseover="handleMouseOver"
        @mouseleave="handleMouseLeave"
        >
        <div class="flex flex-shrink-0 gap-2 items-center">
            <p>
                {{ icon }}
            </p>
            <p 
            class="text-sm font-semibold text-white transition-all duration-300 ease-in-out dark:text-stone-900"
            v-show="isHovered"
            >
                {{ title }}
            </p>
        </div>
        <div
            class="text-sm font-normal text-white transition-all duration-300 ease-in-out dark:text-stone-900"
            v-show="isHovered"
        >
            {{ text }}
        </div>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isHovered: false,
      };
    },
    props: {
      icon: {
        type: String,
        required: true,
      },
      title: {
        type: String,
        required: true,
      },
      text: {
        type: String,
        required: true,
      },
      customClass: {
        type: Array,
        default: 'left-0 origin-bottom-left rounded-bl',
      },
    },
    methods: {
      handleMouseOver() {
        this.isHovered = true;
      },
      handleMouseLeave() {
        this.isHovered = false;
      },
    },
  };
  </script>
  