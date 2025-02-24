<template>
  <div class="sm:pb-10 bg-B4 dark:bg-stone-900 text-stone-900">
    <Layout :showProgress="true">
    <template #content>
      <div class="space-y-3 sm:space-y-4">
        <!-- Hero 區塊 -->
        <div class="grid grid-cols-4 grid-flow-row-dense gap-3 cursor-default sm:gap-4">
          <!-- 第一格 -->
          <div class="inline-flex flex-col col-span-4 gap-6 justify-between p-5 bg-white rounded-2xl xs:gap-10 sm:p-8 sm:col-span-2 sm:rounded-3xl dark:bg-transparent dark:border dark:border-stone-50 text-stone-900 dark:text-white">
            <div class="flex gap-6 items-center text-xl font-bold xs:text-2xl sm:text-3xl lg:text-4xl">
              <!-- 照片 -->
              <div class="hidden overflow-hidden w-32 h-32 bg-amber-100 bg-center bg-cover rounded-full xl:block">
                <img src="https://i.imgur.com/XiOOKB4.jpeg" alt="" class="object-cover object-center w-full">
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
                <ArrowButton @click="isModalOpen = true" :disabled="isLinkDisabled" />
              </div>
              <div class="z-0 w-full h-full bg-center bg-cover transition-transform duration-500 ease-in-out transform hover:scale-110"
              style="background-image: url(https://i.imgur.com/gCveLP0.png)">
              </div>
            </div>
          </div>
          <!-- 第三格 -->
          <a href="https://drive.google.com/file/d/1hF-7DTst3hVZQ1EPWc3Bd9Qo_GsqH2B6/view?usp=sharing" target="_blank" class="hidden overflow-hidden row-span-2 rounded-2xl sm:rounded-3xl lg:block">
            <div class="relative w-full h-full">
              <div class="absolute bottom-0 z-10">
                <ArrowButton link-to="https://drive.google.com/file/d/1hF-7DTst3hVZQ1EPWc3Bd9Qo_GsqH2B6/view?usp=sharing" />
              </div>
              <p class="absolute w-fit h-fit inset-0 z-10 flex items-center justify-center text-6xl font-bold tracking-[.4em] text-white text-outline mx-auto my-auto"
                style="writing-mode: vertical-lr; -webkit-writing-mode: vertical-lr;">
                {{ $t('hero.item9') }}
              </p>
              <div class="w-full h-full bg-center bg-cover brightness-75 transition-transform duration-500 ease-in-out transform -z-10 hover:scale-110 bg-[url('https://images.unsplash.com/photo-1524591431555-cc7876d14adf?q=80&w=2914&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D')]">
              </div>
            </div>
          </a>
          <!-- 第四格 -->
          <div class="col-span-4 lg:col-span-1 sm:col-span-2">
            <CodeTyping />
          </div>
          <!-- 第五格 -->
          <a href="https://www.linkedin.com/in/chen-tina/" target="_blank" class="hidden lg:block">
            <div class="inline-flex justify-center items-center w-full h-full bg-blue-200 rounded-2xl transition-colors duration-200 ease-in-out aspect-square sm:rounded-3xl hover:bg-blue-200/75 group">
              <entypo-social-linkedin class="text-6xl text-white transition-all duration-200 ease-in-out dark:text-stone-900 group-hover:text-7xl"></entypo-social-linkedin>
            </div>
          </a>
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
        <div class="flex flex-col gap-3 cursor-default sm:gap-4">
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
                    {{ $t('work.core.item3') }}
                  </p>
                  <p class="text-lg font-extrabold xs:text-2xl sm:text-3xl">
                    Shape Mask
                  </p>
                </div>
                <RouterLink to="/blog/post/19" class="overflow-hidden relative w-full h-full bg-white rounded-2xl border border-white/20 sm:rounded-3xl">
                  <img src="/plugin-banner.png" alt="" class="object-cover inset-0 w-full h-full transition-all duration-300 lg:absolute hover:scale-105">
                </RouterLink>
              </div>
            </SlideIn> 

            <!-- Blog 區塊 -->
            <SlideIn direction="right">
              <div class="p-5 bg-white rounded-2xl sm:p-8 dark:bg-transparent sm:rounded-3xl dark:border dark:border-white">
                <div class="flex justify-between items-start mb-4 lg:mb-10 xs:mb-6">
                  <p class="tracking-[.25em]  text-xs xs:text-base xl:text-lg font-bold ">
                    {{ $t('work.core.item4') }}
                  </p>
                  <div class="flex justify-end">
                    
                  </div>
                  <WaveButton 
                  linkTo="/blog/blog"
                  :text="$t('work.core.item5')"
                  :borderClass="'border-stone-900 dark:border-white'"
                  :textClass="'text-black dark:text-white'"
                  :hoverTextClass="'dark:group-hover:text-stone-900 group-hover:text-white'"
                  :bgClass="'bg-stone-900 dark:bg-white'"
                  class="transform origin-top-right scale-75 sm:scale-100"
                  />
                </div>
                <div class="space-y-3 text-sm font-extrabold lg:space-y-5 xs:text-2xl">
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
  computed: {
    posts() {
      return [
        {
          id: 1,
          link: '/blog/post/1',
          title: this.$t('post1.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*LSgS3r0VigNdsXHxAx9kqg.png",
          date: "2024．09．02",
        },
        {
          id: 2,
          link: '/blog/post/7',
          title: this.$t('post7.core.title'),
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*yJi3pvZRfffeHToNDhtSmQ.png",
          date: "2024．10．20",
        },
        {
          id: 3,
          link: '/blog/post/14',
          title: this.$t('post14.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*XmqGmjWlFW0ZdY8xyTCGqA.png",
          date: "2024．11．08",
        },
        {
          id: 4,
          link: '/blog/post/15',
          title: this.$t('post15.core.title'),
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*l9LTo-VAunwN9UZeeoca4Q.png",
          date: "2024．11．12",
        }
      ];
    },
    displayedPosts() {
      // lg 尺寸顯示三筆資料，其餘尺寸顯示四筆資料
      return this.windowWidth >= 1024 ? this.posts.slice(0, 3) : this.posts.slice(0, 4);
    }
  }
};
</script>

