<template>
  <div 
  :style="{
      backgroundImage: `url(${backgrounds[activeTab - 1]})`
    }"
  class="flex overflow-hidden flex-col p-6 bg-center bg-no-repeat bg-cover rounded-2xl border cursor-default dark:border-white border-B4 text-stone-900 dark:text-white sm:rounded-3xl h-fit dark:bg-transparent">
    <!-- Top Section -->
    <div class="flex gap-12 items-center px-8 py-3 mb-10 font-semibold bg-white rounded-2xl dark:bg-stone-900">
      <!-- Project Buttons -->
      <button
      v-for="tab in [1, 2, 3]"
      :key="tab"
      type="button"
      class="inline-flex justify-center w-full leading-normal text-center transition-colors duration-300 ease-in-out"
      :class="{
        'text-stone-900  dark:text-white': activeTab === tab, // Active 状态下的颜色
        'text-stone-400 hover:text-stone-900 dark:text-stone-500 dark:hover:text-white': activeTab !== tab // 非 Active 状态颜色
      }"
      @click="selectTab(tab)"
    >
      {{ $t(`work.title.item6-${tab}`) }}
    </button>
    </div>

    <!-- Bottom Section -->
    <div class="p-4 rounded-2xl backdrop-blur-sm bg-white/60 dark:bg-stone-900/40">
      <SkeletonLoader v-if="loading" size="full" />
      <TabTransition v-else>
        <!-- Project 1 -->
        <div
          v-if="activeTab === 1"
          :key="1"
          :activeTab="activeTab"
          @selectTab="selectTab"
        >
        我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。 在初期會議的討論中我們曾小小卡關，營造質感生活、舒適溫馨感，透過使用者的想像，可以使他們在這裡找房源時有良好的使用體驗。
        </div>
        <!-- Project 2 -->
        <div
          v-if="activeTab === 2"
          :key="2"
          :activeTab="activeTab"
          @selectTab="selectTab"
        >
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto natus sit consequatur exercitationem necessitatibus molestias, eius aliquid, iure ad hic delectus enim inventore esse quae pariatur. Sint quaerat, enim consectetur excepturi eum beatae? Similique placeat laborum veritatis libero esse voluptas vero a aperiam possimus minima tempora voluptatum, quae suscipit incidunt?
        </div>
        <!-- Project 3 -->
        <div
          v-if="activeTab === 3"
          :key="3"
          :activeTab="activeTab"
          @selectTab="selectTab"
        >
        我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。 在初期會議的討論中我們曾小小卡關，營造質感生活、舒適溫馨感，透過使用者的想像，可以使他們在這裡找房源時有良好的使用體驗。
        </div>
      </TabTransition>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
  setup() {
    const loading = ref(true);
    const data = ref(null);
    const activeTab = ref(1);

    // 背景圖列表
    const backgrounds = ref([
      'https://images.unsplash.com/photo-1731141028975-3eb6b91cef4c?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
      'https://media.istockphoto.com/id/1043898904/photo/cobblestone-street-stockhom-sweden.webp?a=1&s=612x612&w=0&k=20&c=T51JUb6d8n9Vw56FPhM8SoC0YE5WhMiZL7O883d7mUc=',
      'https://images.unsplash.com/photo-1731141707768-76d857b0f82d?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDd8fHxlbnwwfHx8fHw%3D',
    ]);

    const selectTab = (tab) => {
      activeTab.value = tab;
    };

    onMounted(async () => {
      // Simulate a delay for loading data
      setTimeout(async () => {
        data.value = 'Loaded content here';
        loading.value = false;
      }, 2000);
    });

    return {
      activeTab,
      selectTab,
      loading,
      data,
      backgrounds
    };
  },
};
</script>
