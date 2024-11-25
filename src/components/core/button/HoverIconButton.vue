<template>
    <div class="w-[200px] relative">
        <div
        class="flex overflow-hidden absolute bottom-0 left-0 flex-col gap-3 p-3 px-3.5 text-left rounded-3xl rounded-bl shadow-lg transition-all duration-200 ease-in-out origin-bottom-left cursor-pointer bg-stone-800 dark:bg-B3 hover:p-3.5 w-fit"
        @mouseover="handleMouseOver"
        @mouseleave="handleMouseLeave"
        >
        <div class="flex flex-shrink-0 gap-2">
            <p>
                {{ icon }}
            </p>
            <p 
            class="font-semibold text-white transition-all duration-300 ease-in-out dark:text-stone-900"
            v-show="isHovered"
            >
                {{ title }}
            </p>
        </div>
        <div
            class="text-sm font-normal text-justify text-white transition-all duration-300 ease-in-out dark:text-stone-900"
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
  