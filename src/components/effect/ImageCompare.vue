<template>
    <div
      class="overflow-hidden relative mx-auto w-full rounded-2xl xl:rounded-3xl"
      :class="heightClass"
      @mousemove="updateSliderPosition"
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
            class="absolute top-4 right-4 px-2 py-1 text-sm text-white rounded bg-stone-800"
          >
            Before
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
            class="absolute top-4 right-4 px-2 py-1 text-sm text-white rounded bg-stone-800"
          >
            After
          </span>
        </div>
  
        <!-- 滑動條 -->
        <div
          class="absolute top-0 left-0 h-full bg-transparent pointer-events-none"
          :style="{ left: sliderPosition + '%' }"
        >
          <div class="w-1 h-full bg-gray-800"></div>
          <!-- 圓形把手 -->
          <div
            ref="sliderHandle"
            class="absolute top-1/2 left-1/2 w-6 h-6 bg-white rounded-full border-2 border-gray-800 shadow transform -translate-x-1/2 -translate-y-1/2 cursor-pointer"
            @mousedown="startDrag"
          ></div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      beforeImage: {
        type: String,
        required: true,
      },
      afterImage: {
        type: String,
        required: true,
      },
      height: {
        type: String,
        default: "h-64", // 預設高度
      },
    },
    computed: {
      // 將傳遞的高度類別綁定到 class 屬性
      heightClass() {
        return this.height;
      },
    },
    data() {
      return {
        sliderPosition: 50, // 初始滑動條位置 (百分比)
        isDragging: false, // 是否正在拖曳
        initialMouseX: 0, // 滑鼠初始 X 坐標
        initialSliderPosition: 0, // 初始滑動條位置
      };
    },
    methods: {
      // 開始拖曳
      startDrag(event) {
        this.isDragging = true;
        this.initialMouseX = event.clientX;
        this.initialSliderPosition = this.sliderPosition;
  
        // 監聽鼠標移動和放開事件
        document.addEventListener("mousemove", this.onDrag);
        document.addEventListener("mouseup", this.stopDrag);
        document.addEventListener("mouseleave", this.stopDrag);
      },
  
      // 拖曳過程中更新滑動條位置
      onDrag(event) {
        if (!this.isDragging) return;
  
        const deltaX = event.clientX - this.initialMouseX;
        const container = this.$el;
        const rect = container.getBoundingClientRect();
        const newPosition = this.initialSliderPosition + (deltaX / rect.width) * 100;
        
        this.sliderPosition = Math.min(Math.max(newPosition, 0), 100); // 限制範圍在 0 到 100
      },
  
      // 停止拖曳
      stopDrag() {
        this.isDragging = false;
        document.removeEventListener("mousemove", this.onDrag);
        document.removeEventListener("mouseup", this.stopDrag);
        document.removeEventListener("mouseleave", this.stopDrag);
      },
  
      // 更新滑動條位置 (在非拖曳狀態下)
      updateSliderPosition(event) {
        if (this.isDragging) return; // 當拖曳時，不處理滑動事件
  
        const container = event.currentTarget;
        const rect = container.getBoundingClientRect();
        const position = ((event.clientX - rect.left) / rect.width) * 100;
        this.sliderPosition = Math.min(Math.max(position, 0), 100); // 限制範圍在 0 到 100
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
  