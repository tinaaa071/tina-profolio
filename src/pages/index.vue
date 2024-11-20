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
              <div class="z-0 w-full h-full bg-center bg-cover transition-transform duration-500 ease-in-out transform hover:scale-110"
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
              <div class="w-full h-full bg-center bg-cover brightness-75 transition-transform duration-500 ease-in-out transform -z-10 hover:scale-110 bg-[url('https://images.unsplash.com/photo-1724271366025-5bbfc5fbdb70?q=80&w=2574&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D')]"
              >
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
          <SlideIn direction="bottom">
            <WorkCard />
          </SlideIn>
          <!-- 其他資源 -->
          <div class="grid overflow-hidden grid-cols-1 gap-2.5 cursor-default lg:grid-cols-2 text-stone-900 dark:text-white h-fit sm:gap-4">
            <!-- Plugin 區塊 -->
            <SlideIn direction="left">
              <div class="flex flex-col p-5 h-full bg-white rounded-2xl sm:p-8 dark:bg-transparent sm:rounded-3xl dark:border dark:border-white">
                <div class="flex justify-between mb-4 lg:mb-10 xs:mb-6">
                  <p class="tracking-[.25em] text-xs xs:text-base xl:text-lg font-bold ">
                    {{ $t('work.core.item1') }}
                  </p>
                  <p class="text-lg font-extrabold xs:text-2xl sm:text-3xl">
                    Shape Mask
                  </p>
                </div>
                <RouterLink to="/" class="overflow-hidden relative w-full h-full bg-white rounded-2xl border border-white/20 sm:rounded-3xl">
                  <img src="/plugin-banner.png" alt="" class="object-cover inset-0 w-full h-full transition-all duration-300 lg:absolute hover:scale-105">
                </RouterLink>
              </div>
            </SlideIn> 

            <!-- Blog 區塊 -->
            <SlideIn direction="right">
              <div class="p-5 bg-white rounded-2xl sm:p-8 dark:bg-transparent sm:rounded-3xl dark:border dark:border-white">
                <div class="flex justify-between items-start mb-4 lg:mb-10 xs:mb-6">
                  <p class="tracking-[.25em]  text-xs xs:text-base xl:text-lg font-bold ">
                    {{ $t('work.core.item1') }}
                  </p>
                  <div class="flex justify-end">
                    
                  </div>
                  <WaveButton 
                  linkTo="/blog/blog"
                  :text="$t('work.core.item2')"
                  :borderClass="'border-stone-900 dark:border-white'"
                  :textClass="'text-black dark:text-white'"
                  :hoverTextClass="'dark:group-hover:text-stone-900 group-hover:text-white'"
                  :bgClass="'bg-stone-900 dark:bg-white'"
                  class="transform origin-top-right scale-75 sm:scale-100"
                  />
                </div>
                <div class="space-y-3 text-sm font-extrabold lg:space-y-5 xs:text-2xl text-stone-400 dark:text-stone-400">
                  <!-- Project Card -->
                  <!-- <RouterLink
                    v-for="(date, index) in ['2024.06.12', '2024.06.12', '2024.06.12', '2024.06.12']"
                    :key="date"
                    :to="`/blog/post/${index + 1}`"
                    class="inline-flex gap-6 w-full leading-normal text-left transition-colors duration-300 ease-in-out focus:text-stone-900 hover:text-stone-900 dark:focus:text-white dark:hover:text-white text-stone-400"
                  >
                    <time class="whitespace-nowrap">
                      {{ `${date}` }}
                    </time>
                    <p class="w-full text-wrap overflow-wrap break-word line-clamp-2">
                      {{ $t('post1.item1') }}
                    </p>
                  </RouterLink> -->
                  <div class="grid grid-cols-2 gap-4 xs:grid-cols-4 lg:grid-cols-3 h-fit">
                    <PostCard 
                      v-for="post in displayedPosts" 
                      :key="post.id" 
                      :post="post" 
                      :showTag="true"
                      :linkTo="post.link"
                      aspectRatio="aspect-[4/5] group-hover:-translate-y-1 transition-transform duration-200 sm:rounded-3xl rounded-2xl"
                    />
                  </div>
                </div>
              </div>
            </SlideIn>
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
import { ref, computed, onMounted, onBeforeUnmount } from 'vue';

export default {
  setup() {
    const isModalOpen = ref(false);
    const windowWidth = ref(window.innerWidth);

    const handleResize = () => {
      windowWidth.value = window.innerWidth;
    };

    onMounted(() => {
      window.addEventListener('resize', handleResize);
    });

    onBeforeUnmount(() => {
      window.removeEventListener('resize', handleResize);
    });

    return { isModalOpen, windowWidth };
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          link: '/blog/post/1',
          title: "Post 1",
          category: this.$t('blog.item3'),
          image: "https://images.unsplash.com/photo-1628768534904-cf74bc8b897d?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          date: "2024．09．02",
        },
        {
          id: 2,
          link: '/about',
          title: "Post 2",
          category: this.$t('blog.item2'),
          image: "https://images.unsplash.com/photo-1628768534895-ff9185e7edbc?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          date: new Date().toLocaleDateString(),
        },
        {
          id: 3,
          link: '/blog/post/3',
          title: "Post 3",
          category: this.$t('blog.item3'),
          image: "https://images.unsplash.com/photo-1628766416710-61d6f15f32b9?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          date: new Date().toLocaleDateString(),
        },
        {
          id: 4,
          link: '/post/1',
          title: "Post 4",
          category: this.$t('blog.item4'),
          image: "https://images.unsplash.com/photo-1723920515274-ace3503adad6?q=80&w=2826&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          date: new Date().toLocaleDateString(),
        }
      ],
    };
  },
  computed: {
    displayedPosts() {
      // lg 尺寸顯示三筆資料，其餘尺寸顯示四筆資料
      return this.windowWidth >= 1024 ? this.posts.slice(0, 3) : this.posts.slice(0, 4);
    }
  }
};
</script>
