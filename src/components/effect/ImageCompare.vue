<template>
    <div
      class="overflow-hidden relative mx-auto w-full rounded-2xl xl:rounded-3xl"
      :class="heightClass"
      @mousemove="updateSliderPosition" 
      @touchstart="startTouch" 
      @touchmove="moveTouch" 
      @touchend="endTouch" 
    >
      <!-- 圖片容器 -->
      <div class="overflow-hidden relative w-full h-full">
        <!-- Before 圖片 -->
        <div class="relative w-full h-full">
          <img
            :src="beforeImage"
            alt="Before"
            class="object-cover w-full h-full"
          />
          <!-- Before 標籤 -->
          <span
            class="absolute top-4 right-4 px-2 py-1 text-sm bg-white rounded dark:text-white text-stone-800 dark:bg-stone-800"
          >
            {{ beforeText }}
          </span>
        </div>
    
        <!-- After 圖片 -->
        <div
          class="absolute top-0 left-0 w-full h-full"
          :style="{
            clipPath: `inset(0 ${100 - sliderPosition}% 0 0)`
          }"
        >
          <img
            :src="afterImage"
            alt="After"
            class="object-cover w-full h-full"
          />
          <!-- After 標籤 -->
          <span
            class="absolute top-4 right-4 px-2 py-1 text-sm bg-white rounded dark:text-white text-stone-800 dark:bg-stone-800"
          >
            {{ afterText }}
          </span>
        </div>
    
        <!-- 滑動條 -->
        <div
          class="absolute top-0 left-0 h-full bg-transparent pointer-events-none"
          :style="{ left: sliderPosition + '%' }"
        >
          <div class="w-1 h-full bg-white dark:bg-stone-800"></div>
          <!-- 圓形把手 -->
          <div
            class="absolute top-1/2 left-1/2 w-5 h-5 bg-white rounded-full transform -translate-x-1/2 -translate-y-1/2 dark:bg-stone-800"
          ></div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      beforeText: {
        type: String,
        default: 'Before',
      },
      afterText: {
        type: String,
        default: 'After',
      },
      beforeImage: {
        type: String,
        required: true,
      },
      beforeImage: {
        type: String,
        required: true,
      },
      afterImage: {
        type: String,
        required: true,
      },
      heightClass: {
        type: String,
        default: "h-64", // 預設高度
      },
    },
    data() {
      return {
        sliderPosition: 50, // 初始滑動條位置 (百分比)
        isTouching: false, // 用來判斷是否在觸控模式
        startTouchX: 0, // 觸控開始的 X 坐標
      };
    },
    methods: {
      updateSliderPosition(event) {
        if (!this.isTouching) {
          const container = event.currentTarget;
          const rect = container.getBoundingClientRect();
          const position = ((event.clientX - rect.left) / rect.width) * 100;
          this.sliderPosition = Math.min(Math.max(position, 0), 100); // 限制範圍在 0 到 100
        }
      },
      // 手機版觸控事件
      startTouch(event) {
        if (event.touches.length === 1) {
          this.isTouching = true;
          this.startTouchX = event.touches[0].clientX;
        }
      },
      moveTouch(event) {
        if (this.isTouching) {
          const container = event.currentTarget;
          const rect = container.getBoundingClientRect();
          const position = ((event.touches[0].clientX - rect.left) / rect.width) * 100;
          this.sliderPosition = Math.min(Math.max(position, 0), 100); // 限制範圍在 0 到 100
        }
      },
      endTouch() {
        this.isTouching = false;
      },
    },
  };
  </script>
  
  <style scoped>
  /* 禁用選擇文本 */
  .no-select {
    user-select: none;
  }
  </style>
  