<template>
  <div class="grid overflow-hidden grid-cols-1 rounded-2xl cursor-default lg:grid-cols-2 text-stone-900 dark:text-white sm:rounded-3xl h-fit dark:bg-transparent dark:border dark:border-white">
    <!-- Left Section -->
    <div class="p-5 bg-white sm:p-8 dark:bg-transparent">
      <p class="tracking-[.25em] lg:mb-10 mb-4 xs:mb-6 text-xs xs:text-base xl:text-lg font-bold ">
        {{ $t('work.core.item1') }}
      </p>
      <div class="space-y-3 text-lg font-extrabold lg:space-y-5 xs:text-2xl text-stone-400 dark:text-stone-400">
        <!-- Project Buttons -->
        <button
          v-for="tab in [1, 2, 3, 4, 5]"
          :key="tab"
          type="button"
          class="inline-flex w-full leading-normal text-left transition-colors duration-300 ease-in-out"
          :class="{
            'text-stone-900 dark:text-white': activeTab === tab,
            'focus:text-stone-900 hover:text-stone-900 dark:focus:text-white dark:hover:text-white': activeTab !== tab
          }"
          @click="selectTab(tab)"
        >
          <p class="whitespace-nowrap">{{ `0${tab} -` }}&nbsp;</p>
          {{ $t(`project${tab}.core.title`) }}
        </button>
      </div>
    </div>

    <!-- Right Section -->
    <div class="h-72 sm:h-96 lg:h-auto">
      <SkeletonLoader v-if="loading" size="full" />
      <TabTransition v-else>
        <!-- Project 1 -->
        <WorkDetail
          v-if="activeTab === 1"
          :key="1"
          :activeTab="activeTab"
          @selectTab="selectTab"
          year="2024"
          :title="$t('project1.core.title')"
          :desc="$t('project1.core.desc')"
          :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3')]"
          linkTo="/work/project1"
          backgroundImage="https://i.imgur.com/I9WoGsH.png"
        />
        <!-- Project 2 -->
        <WorkDetail
          v-if="activeTab === 2"
          :key="2"
          :activeTab="activeTab"
          @selectTab="selectTab"
          year="2024"
          :title="$t('project2.core.title')"
          :desc="$t('project2.core.desc')"
          :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3'), $t('projectTag.item8')]"
          linkTo="/work/project2"
          backgroundImage="https://i.imgur.com/mVThtnS.png"
        />
        <!-- Project 3 -->
        <WorkDetail
          v-if="activeTab === 3"
          :key="3"
          :activeTab="activeTab"
          @selectTab="selectTab"
          year="2024"
          :title="$t('project3.core.title')"
          :desc="$t('project3.core.desc')"
          :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3'), $t('projectTag.item6')]"
          linkTo="/work/project3"
          backgroundImage="https://i.imgur.com/KYGZdtx.png"
        />
        <!-- Project 4 -->
        <WorkDetail
          v-if="activeTab === 4"
          :key="4"
          :activeTab="activeTab"
          @selectTab="selectTab"
          year="2024"
          :title="$t('project4.core.title')"
          :desc="$t('project4.core.desc')"
          :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3'), $t('projectTag.item5'), $t('projectTag.item7')]"
          linkTo="/work/project4"
          backgroundImage="https://i.imgur.com/NcNbePH.png"
        />
        <!-- Project 5 -->
        <WorkDetail
          v-if="activeTab === 5"
          :key="5"
          :activeTab="activeTab"
          @selectTab="selectTab"
          year="2023"
          :title="$t('project5.core.title')"
          :desc="$t('project5.core.desc')"
          :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item4'), $t('projectTag.item6')]"
          linkTo="/work/project5"
          backgroundImage="https://i.imgur.com/Xpsuh1Z.png"
        />
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
    };
  },
};
</script>
