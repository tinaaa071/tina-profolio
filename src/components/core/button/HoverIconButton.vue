<template>
    <div class="w-[200px] relative">
        <div
        class="flex overflow-hidden absolute right-0 bottom-0 flex-col gap-3 p-3 px-3.5 text-left rounded-3xl rounded-br-none shadow-lg transition-all duration-200 ease-in-out origin-bottom-right bg-B6 hover:p-3.5 w-fit"
        @mouseover="handleMouseOver"
        @mouseleave="handleMouseLeave"
        >
        <div class="flex-shrink-0">
            {{ icon }}
        </div>
        <div
            class="text-sm text-justify text-white transition-all duration-300 ease-in-out"
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
  