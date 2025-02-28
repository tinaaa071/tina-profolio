<template>
    <div class="cursor-default">
      <!-- title -->
      <div class="relative z-10 mb-4 sm:mb-6">
        <h1 class="text-2xl font-semibold text-center text-white dark:text-stone-900 lg:text-5xl sm:text-4xl">
          {{ title }}
        </h1>
        <!-- tools -->
        <IconGroup 
          :iconsVisible="iconsVisible" 
          class="hidden absolute bottom-0 right-5 xs:block" 
        />
      </div>
      <!-- Info -->
      <div class="flex flex-col gap-6 px-6 py-8 w-full lg:gap-10 bg-B4 dark:bg-stone-800 text-stone-800 sm:gap-8 xl:px-28 md:p-10 xl:py-14 dark:text-white dark:border-white/20 dark:border-b">
        <!-- Tag + BTN -->
        <div class="flex justify-between items-center">
          <!-- Tag -->
          <div class="flex flex-wrap gap-2 sm:gap-3">
            <Tag :tag="tag" class="bg-white" />
          </div>
          <!-- BTN -->
          <MagneticButton 
            v-if="showBTN"
            :linkTo="linkTo" 
            :linkType="linkType" 
            :icon="icon" 
            :text="$t('work.core.item5')"
            class="hidden xs:block"
            />
        </div>
        <!-- Title -->
        <h2 class="text-2xl font-bold lg:text-5xl sm:text-4xl">
          {{ title }}
        </h2>
        <!-- Info Sections -->
        <div class="grid grid-cols-1 gap-4 sm:gap-8 xs:grid-cols-2 lg:grid-cols-4">
          <div>
            <p class="mb-1 font-semibold sm:mb-2">{{ $t('work.info.item1') }}</p>
            <p class="font-normal">{{ info1 }}</p>
          </div>
          <div>
            <p class="mb-1 font-semibold sm:mb-2">{{ $t('work.info.item2') }}</p>
            <ul class="font-normal list-none list-inside">
              <li v-for="(info2, index) in info2" :key="index" >
                {{ info2 }}
              </li>
            </ul>
          </div>
          <div>
            <p class="mb-1 font-semibold sm:mb-2">{{ $t('work.info.item3') }}</p>
            <p class="font-normal">{{ info3 }}</p>
          </div>
          <div>
            <p class="mb-1 font-semibold sm:mb-2">{{ $t('work.info.item4') }}</p>
            <p class="font-normal">{{ info4 }}</p>
          </div>
        </div>
        <!-- BTN -->
        <MagneticButton 
            v-if="showBTN"
            :linkTo="linkTo" 
            :linkType="linkType"
            :icon="icon" 
            :text="$t('work.core.item5')"
            class="xs:hidden"
            />
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        required: true,
      },
      info1: {
        type: String,
        required: true,
      },
      info2: {
        type: [String, Array],
        required: true,
      },
      info3: {
        type: String,
        required: true,
      },
      info4: {
        type: String,
        required: true,
      },
      tag: {
        type: Array,
        required: true,
      },
      iconsVisible: {
        type: Array,
        default: () => [false, false, false, false, false],
      },
      linkTo: {
        type: String,
        required: true,
      },
      linkType: {
      type: String,
      default: 'router-link', // 支援 'router-link' 或 'a'
      validator: (value) => ['router-link', 'a'].includes(value),
    },
      icon: {
        type: [Object, Function],
        required: true,
        },
      showIcon: {
        type: Boolean,
        default: true,
       },
      showBTN: {
        type: Boolean,
        default: true,
       },
    }
  };
  </script>
  