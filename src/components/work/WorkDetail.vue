<template>
    <div  class="relative w-full h-full">
      <div class="flex absolute top-0 left-0 flex-col justify-between p-5 w-full h-full text-white backdrop-blur-lg transition-all duration-300 ease-in-out lg:opacity-0 sm:p-8 bg-stone-900/20 lg:hover:opacity-100">
        <div class="space-y-5 cursor-default">
          <div class="space-y-3">
            <p class="text-xs font-medium xs:text-base xl:text-lg tracking-[.25em]">
            {{ year }}
            </p>
            <p class="text-lg font-bold xs:text-2xl sm:text-3xl">
              {{ title }}
            </p>
            <p class="hidden text-xl font-light md:block">
              {{ desc }}
            </p>
          </div>
          <div class="flex gap-2 sm:gap-3">
            <Tag 
            :tag="tag"
            class="bg-white dark:bg-white dark:text-zinc-900" 
            />
          </div>
        </div>
        <WaveButton 
        :linkTo="linkTo" 
        :text="$t('work.core.item2')"
        class="transform origin-left scale-75 sm:scale-100"
        />
      </div>
      <div class="w-full h-full bg-center bg-cover"
      :style="{ backgroundImage: `url(${backgroundImage})` }">
    </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      activeTab: {
        type: Number,
        required: true
      },
      year: {
        type: String,
        required: true
      },
      title: {
        type: String,
        required: true
      },
      desc: {
        type: String,
        required: true
      },
      backgroundImage: {
        type: String,
        required: true
      },
      linkTo: {
      type: String,
      required: true,
      },
      tag: {
        type: Array,
        required: true,
      },
    }
  };
</script>
  