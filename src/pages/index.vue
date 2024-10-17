<template>
  <div class="sm:pb-10 bg-B4 dark:bg-stone-900 text-stone-900">
    <Layout :showProgress="true">
    <template #content>
      <div class="space-y-5 sm:space-y-8">
        <!-- Hero 區塊 -->
        <div class="grid grid-cols-4 grid-flow-row-dense gap-2.5 cursor-default sm:gap-4">
          <!-- 第一格 -->
          <div class="inline-flex flex-col col-span-4 gap-6 justify-between p-5 bg-white rounded-2xl xs:gap-10 sm:p-8 sm:col-span-2 sm:rounded-3xl dark:bg-transparent dark:border dark:border-stone-50 text-stone-900 dark:text-white">
            <div class="flex gap-6 items-center text-xl font-bold xs:text-2xl sm:text-3xl lg:text-4xl">
              <!-- 照片 -->
              <div class="hidden w-32 h-32 bg-center bg-cover rounded-full xl:block"
              style="background-image: url(https://images.unsplash.com/photo-1723920515274-ace3503adad6?q=80&w=2826&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)">
              </div>
              <div>
                <p class="mb-2 leading-tight sm:leading-normal text-balance">
                  {{ $t('hero.item1') }}
                </p>
                <p class="inline-flex leading-tight sm:flex-col md:flex-row sm:leading-normal">
                  {{ $t('hero.item2') }}
                  <Typewriter class="ml-2 md:ml-2 sm:ml-0" />
                </p>
              </div>
            </div>
            <div class="inline-flex justify-between w-full text-sm font-normal">
              <p>{{ $t('hero.item6') }}</p>
              <p class="hidden lg:block">{{ $t('hero.item7') }}</p>
              <p>{{ $t('hero.item8') }}</p>
            </div>
          </div>
          <!-- 第二格 -->
          <div class="overflow-hidden col-span-2 rounded-2xl cursor-pointer sm:rounded-3xl lg:col-span-1"
          @click="isModalOpen = true"
          >
            <div class="relative w-full h-full">
              <div class="absolute bottom-0 z-10">
                <ArrowButton link-to="" @click="isModalOpen = true" />
              </div>
              <div class="z-0 w-full h-full bg-center bg-cover rounded-3xl transition-transform duration-500 ease-in-out transform hover:scale-110"
              style="background-image: url(https://images.unsplash.com/photo-1723920515274-ace3503adad6?q=80&w=2826&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)">
              </div>
            </div>
          </div>
          <!-- 第三格 -->
          <RouterLink to="/" class="hidden overflow-hidden row-span-2 rounded-2xl sm:rounded-3xl lg:block">
            <div class="relative w-full h-full">
              <div class="absolute bottom-0 z-10">
                <ArrowButton link-to="/" />
              </div>
              <p class="absolute w-fit h-fit inset-0 z-10 flex items-center justify-center text-6xl font-bold tracking-[.4em] text-white text-outline mx-auto my-auto"
              style="writing-mode: vertical-lr; -webkit-writing-mode: vertical-lr;"
              >
              {{ $t('hero.item9') }}
              </p>
              <div class="w-full h-full bg-center bg-cover rounded-3xl brightness-75 transition-transform duration-500 ease-in-out transform -z-10 hover:scale-110"
              style="background-image: url(https://images.unsplash.com/photo-1724271366025-5bbfc5fbdb70?q=80&w=2574&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)">
              </div>
            </div>
          </RouterLink>
          <!-- 第四格 -->
          <div class="col-span-4 lg:col-span-1 sm:col-span-2">
            <CodeTyping />
          </div>
          <!-- 第五格 -->
          <RouterLink to="/" class="hidden lg:block">
            <div class="inline-flex justify-center items-center w-full h-full bg-blue-200 rounded-2xl transition-colors duration-200 ease-in-out aspect-square sm:rounded-3xl hover:bg-blue-200/75 group">
              <entypo-social-linkedin class="text-6xl text-white transition-all duration-200 ease-in-out dark:text-stone-900 group-hover:text-7xl" />
            </div>
          </RouterLink>
          <!-- 第六格 -->
          <div class="col-span-2 p-5 bg-white rounded-2xl md:p-8 sm:rounded-3xl dark:bg-transparent dark:border dark:border-stone-50 text-stone-900 dark:text-white lg:col-span-1">
            <p class="mb-4 text-xs font-bold sm:text-sm md:text-lg">
              {{ $t('hero.item10') }}
            </p>
            <p class="text-xl font-extrabold leading-normal sm:leading-normal xs:leading-normal xs:text-2xl sm:text-3xl lg:text-4xl lg:leading-normal">
              {{ $t('hero.item11') }}
            </p>
          </div>
          <!-- Marquee -->
          <div class="col-span-4">
            <Marquee />
          </div>
        </div>
        <!-- Works 區塊 -->
        <div class="flex flex-col gap-2.5 cursor-default sm:gap-4">
          <!-- Works -->
          <WorkCard />
          <!-- 其他資源 -->
          <div class="grid overflow-hidden grid-cols-1 gap-2.5 cursor-default lg:grid-cols-2 text-stone-900 dark:text-white h-fit dark:bg-transparent dark:border dark:border-white sm:gap-4">
            <!-- Plugin 區塊 -->
            <div class="p-5 bg-white rounded-2xl sm:p-8 dark:bg-transparent sm:rounded-3x">
              <div class="flex justify-between mb-4 lg:mb-10 xs:mb-6">
                <p class="tracking-[.25em] text-xs xs:text-base xl:text-lg font-bold ">
                  {{ $t('work.core.item1') }}
                </p>
                <p class="text-lg font-extrabold xs:text-2xl sm:text-3xl lg:sm:text-4xl">
                  Shape Mask
                </p>
              </div>
              <RouterLink to="/">
                <div class="overflow-hidden rounded-2xl sm:rounded-3xl">
                  <img src="../assets/plugin-banner.png" alt="" class="transition-all duration-300 hover:scale-105">
                </div>
              </RouterLink>
            </div>

            <!-- Blog 區塊 -->
            <div class="p-5 bg-white rounded-2xl sm:p-8 dark:bg-transparent sm:rounded-3xl">
              <p class="tracking-[.25em] lg:mb-10 mb-4 xs:mb-6 text-xs xs:text-base xl:text-lg font-bold ">
                {{ $t('work.core.item1') }}
              </p>
              <div class="space-y-3 text-lg font-extrabold lg:space-y-5 xs:text-2xl sm:text-3xl lg:sm:text-4xl text-stone-400 dark:text-stone-400">
                <!-- Project Buttons -->
                 <RouterLink to="">
                  
                 </RouterLink>
                <button
                  v-for="tab in [1, 2, 3, 4]"
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
          </div>
        </div>
      </div>
    </template>
  </Layout>
  </div>
  <Footer />
  <Modal :show="isModalOpen" @close="isModalOpen = false">
    <Spline />
  </Modal>
</template>

<script>
import { ref } from 'vue';

export default {
  setup(props) {
      const isModalOpen = ref(false)
      
      return { isModalOpen }
    }
};
</script>