<template> 
     <div class="relative pb-6 text-sm sm:pb-10 bg-B4 dark:bg-stone-900 text-stone-800 xs:text-base dark:text-white">
      <Navbar />
      <ProgressBar />
      <BackToTop class="z-20" />
      <!-- Banner -->
      <Banner 
        bannerSrc="https://i.imgur.com/YISZdyR.jpeg"
      />
      <!-- Content -->
      <div class="absolute left-0 sm:top-[480px] top-[400px] w-full leading-relaxed">
        <!-- Info -->
        <Info 
        :title="$t('project3.core.title')"
        :info1="'2024.06 - 2024.12'"
        :info2="[$t('project3.team.item1')]" 
        :info3="$t('project3.info.item3')"
        :info4="$t('project3.info.item1')"
        :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3'), $t('projectTag.item6')]" 
        :iconsVisible="[true, false, false, true, true, true, true, false, false]"
        :linkTo="'/'"
        :icon="icon" 
        
        />
        <!-- Main Content -->
        <div>
          <ScrollSpy :sections="sections" />
          <!-- 專案資訊 -->
          <Section1
          id="section1"
          :info1="$t('project3.info.item1')"
          :info2="[$t('project3.demand.item1'), $t('project3.demand.item2'), $t('project3.demand.item3'), $t('project3.demand.item4')]"
          :info4="[
            { avatarSrc: 'https://i.imgur.com/93zadWo.png', job: $t('project3.team.item1'), name: 'Tina Chen' },
            { avatarSrc: 'https://i.imgur.com/ZJwqurr.png', job: $t('project3.team.item5'), name: 'Rowena Hsu' },
            { avatarSrc: 'https://i.imgur.com/fBGnJUp.png', job: $t('project3.team.item2'), name: 'William Chou' },
            { avatarSrc: 'https://i.imgur.com/vEcl0rw.png', job: $t('project3.team.item3'), name: 'David Huang' }
          ]"
          :content="$t('project3.brief.item1')"
          bannerSrc="https://i.imgur.com/iRYE8Qr.pngD"
          >
            <ul class="leading-loose list-disc list-inside">
              <li>
                <span class="font-semibold">
                  {{ $t('project3.brief.item2') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project3.brief.item2-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project3.brief.item3') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project3.brief.item3-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project3.brief.item4') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project3.brief.item4-1') }}
                </span>
              </li>
            </ul>
          </Section1>
          <!-- 專案概覽 -->
          <Section2
            id="section2"
            :briefs="[
            { title: $t('work.title.item2-1'), content: $t('project3.briefCard.item1') },
            { title: $t('work.title.item2-2'), content: $t('project3.briefCard.item2') },
            { title: $t('work.title.item2-3'), content: $t('project3.briefCard.item3') },
            { title: $t('work.title.item2-4'), content: $t('project3.briefCard.item4') }
          ]"
          />
          <!-- 分隔 -->
          <Dot />
          <!-- 專案背景 -->
          <Section3
            id="section3"
            :title="$t('work.title.item3')"
          >
            <template #content-1>
              <div>
                <p class="mb-6 font-normal">
                  {{ $t('project3.background.item1') }}
                </p>
                <Parallax
                backgroundImage="https://images.unsplash.com/photo-1648792940059-3b782a7b8b20?q=80&w=2832&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                speed="0.08"
                customClass="rounded-2xl xl:rounded-3xl aspect-video sm:bg-contain bg-cover"
              />
              </div>
            </template>
          </Section3>
          <!-- 設計流程 -->
          <!-- <section id="section4" >
            <Parallax 
            class="h-96"
            backgroundImage="https://images.unsplash.com/photo-1731141028975-3eb6b91cef4c?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            />
          </section> -->
          <!-- 專案目標 -->
          <Section3
            id="section5"
            :title="$t('work.title.item5')"
          >
            <template #content-1>
              <StackCard
                :cards="[1, 2]"
                :cardColors="['bg-stone-900 dark:bg-B3', 'bg-B3 dark:bg-stone-700']"
                :scrollEndOffset="480"
              >
                <template #card0>
                  <div class="text-white dark:text-stone-900">
                    <p class="mb-4 font-semibold md:mb-6 sm:mb-8 md:text-xl">
                      {{ $t('work.title.item5-2') }}
                    </p>
                    <List  
                    numClass="dark:bg-stone-700 dark:text-white bg-stone-500"
                    :items="[
                        { title: $t('project3.goal.item1') },
                        { title: $t('project3.goal.item2') },
                        { title: $t('project3.goal.item3') }
                      ]"
                    />
                  </div>
                </template>
                <template #card1>
                  <div class="dark:text-white text-stone-900">
                    <p class="mb-4 font-semibold md:mb-6 sm:mb-8 md:text-xl">
                      {{ $t('work.title.item5-1') }}
                    </p>
                    <List
                    :items="[
                        { title: $t('project3.problem.item1') },
                        { title: $t('project3.problem.item2') },
                        { title: $t('project3.problem.item3') },
                      ]"
                    />
                  </div>
                </template>
              </StackCard>
            </template>
          </Section3>
          <!-- 前期研究 -->
          <Section3
            id="section6"
            :title="$t('work.title.item6')"
          >
            <template #content-1>
              <TabCard :buttons="['work.title.item6-1', 'work.title.item6-2']">
                <!-- Background Images -->
                <template #backgrounds>
                  <img src="https://images.unsplash.com/photo-1434030216411-0b793f4b4173?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://images.unsplash.com/photo-1505751172876-fa1923c5c528?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <div v-if="activeTab === 1">
                    <List 
                    :items="[
                        { title: $t('project3.sa.item1') },
                        { title: $t('project3.sa.item2') },
                        { title: $t('project3.sa.item3') }
                      ]"
                    />
                  </div>
                  <div v-if="activeTab === 2">
                    <Ta
                      :cards="[
                        { avatarSrc: 'https://images.unsplash.com/photo-1573496130141-209d200cebd8?q=80&w=2938&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', title: $t('project3.ta.item1'), content: $t('project3.ta.item1-1') }
                      ]"
                    />
                    <!-- <Persona 
                    avatarSrc="https://images.unsplash.com/photo-1527613426441-4da17471b66d?q=80&w=2904&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                    :items="{
                      u1: [$t('projectTag.item1'), $t('projectTag.item2')],
                      u2: ['User 2 item 1', 'User 2 item 2', 'User 2 item 3'],
                      u3: ['User 3 item 1']
                    }"
                    /> -->
                  </div>
                </template>
              </TabCard>
            </template>
          </Section3>
          <!-- 圖片 -->
          <EnlargeImg class="mx-auto" imageUrl="https://images.unsplash.com/photo-1641903202531-bfa6bf0c6419?q=80&w=2832&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
          <!-- 設計發想 -->
          <Section3
            id="section8"
            :title="$t('work.title.item9')"
          >
            <template #content-1>
              <CardTilt @click="isModalOpen = true" class="cursor-pointer">
                <img 
                  src="https://i.imgur.com/E3rF3z9.png"
                  alt="SiteMap"
                  class="object-cover w-full rounded-xl"
                >
              </CardTilt>
            </template>
          </Section3>
          <!-- 設計原則 -->
          <Section3
            id="section9"
            :title="$t('work.title.item10')"
          >
            <template #content-1>
              <List 
                customClass="px-6 py-5 bg-B3 rounded-2xl xl:rounded-3xl dark:bg-transparent dark:border dark:border-white"
                :items="[
                    { title: $t('project3.principle.item1'), content: $t('project3.principle.item1-1') },
                    { title: $t('project3.principle.item2'), content: $t('project3.principle.item2-1') },
                    { title: $t('project3.principle.item3'), content: $t('project3.principle.item3-1') },
                    { title: $t('project3.principle.item4'), content: $t('project3.principle.item4-1') }
                  ]"
                />
            </template>
          </Section3>
          <!-- Banner -->
          <Parallax 
            class="md:h-[500px] h-64"
            backgroundImage="https://i.imgur.com/HmgbUQI.png"
            />
          <!-- 設計產出 -->
          <Section3
            id="section11"
            :title="$t('work.title.item11')"
          >
            <!-- Design System -->
            <template #content-1>
              <div class="font-normal">
                <CardTilt>
                  <img 
                      src="https://i.imgur.com/8G5ve6S.png"
                      alt="Banner"
                      class="object-cover mb-8 w-full rounded-2xl xl:rounded-3xl aspect-video"
                    >
                </CardTilt>
                <p 
                v-html="$t('project3.system.item1')"
                class="text-justify"
                >
                </p>
                <br>
                <ListNum :items="[
                  {title: $t('project3.system.item2'), description:  $t('project3.system.item2-1')},
                  {title: $t('project3.system.item3'), description:  $t('project3.system.item3-1')},
                  {title: $t('project3.system.item4'), description:  $t('project3.system.item4-1')}
                  ]" />
              </div>
            </template>  
            <!-- Mockup -->
            <template #content-2>
              <div class="bg-B5 dark:bg-stone-700">
                <TabCard 
                  class="p-6 border-none xl:px-56 md:px-10 md:py-8"
                  :customClass="[bg-transparent, p-0]"
                  :scrollableClass="'overflow-x-auto whitespace-nowrap'"
                  :buttonClass="'w-1/2'"
                  :buttons="['project3.mockup.tab.item1', 'project3.mockup.tab.item2', 'project3.mockup.tab.item3', 'project3.mockup.tab.item4', 'project3.mockup.tab.item5']">
                    <!-- Tab Contents -->
                    <template #default="{ activeTab }">
                      <div v-if="activeTab === 1" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/AyXWZeG.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute -right-56 top-[3%] lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project3.mockup.info.item1')"
                            :text="$t('project3.mockup.info.item1-1')"
                            />
                          </div>
                          <div class="hidden absolute -right-56 top-1/2 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project3.mockup.info.item2')"
                            :text="$t('project3.mockup.info.item2-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 2" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/y5fzHf2.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute -left-56 top-[40%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project3.mockup.info.item3')"
                            :text="$t('project3.mockup.info.item3-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/u5altnC.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                        </div>
                      </div>
                      <div v-if="activeTab === 3" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/2oUhNK5.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute -right-56 top-1/3 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project3.mockup.info.item4')"
                            :text="$t('project3.mockup.info.item4-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 4" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/8sA4xOq.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[15%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project3.mockup.info.item6')"
                            :text="$t('project3.mockup.info.item6-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[30%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project3.mockup.info.item5')"
                            :text="$t('project3.mockup.info.item5-1')"
                            />
                          </div>
                        </div>
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/dtaFonL.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[25%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project3.mockup.info.item7')"
                            :text="$t('project3.mockup.info.item7-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/BYgRLkm.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[25%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project3.mockup.info.item8')"
                            :text="$t('project3.mockup.info.item8-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 5" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/zNE2bo8.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[15%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project3.mockup.info.item9')"
                            :text="$t('project3.mockup.info.item9-1')"
                            />
                          </div>
                        </div>
                      </div>
                    </template>
                </TabCard>
              </div>
            </template>
            <!-- Prototype -->
            <template #content-3>
              <div class="bg-B3 dark:bg-stone-600">
                <div class="p-6 border-none xl:px-56 md:px-10 md:py-8">
                  <div class="pb-6 xs:pb-12 lg:pb-16">
                    <div class="flex relative justify-center items-center w-full h-full">
                      <!-- 影片B，寬度90%，保持比例縮放 -->
                      <Video
                        videoSrc="https://www.youtube.com/embed/_6jO-zrU5Do?autoplay=1&mute=1&loop=1"
                        class="top-1 sm:top-2 w-[77%] sm:w-[64%] xl:w-[77%] object-contain"
                        videoClass="aspect-[8/5]"
                      />
                      
                      <!-- 圖片A，寬度90%，保持比例縮放 -->
                      <img
                        ref="image"
                        src="https://i.imgur.com/KVpYsAZ.png"
                        alt="Image A"
                        class="object-contain absolute top-0 left-1/2 transform -translate-x-1/2 sm:w-[80%] xl:w-[96%] w-[96%]"
                      />
                    </div>
                  </div>
                </div>
              </div>
            </template>
          </Section3>
          <!-- 設計交付 -->
          <Section3
            id="section12"
            :title="$t('work.title.item12')"
          >
            <template #content-1>
              <CardTilt>
                  <img 
                  src="https://i.imgur.com/I1CWKDQ.png"
                  class="object-cover mb-8 w-full rounded-2xl xl:rounded-3xl aspect-video"
                >
              </CardTilt>
            <p v-html="$t('project3.handoff.item1')" class="font-normal"></p>
            </template>
          </Section3>
          <!-- 反饋與學習 -->
          <Section3
            id="section14"
            :title="$t('work.title.item14')"
          >
            <template #content-1>
              <CardTilt>
                    <img 
                    src="https://i.imgur.com/YISZdyR.jpeg"
                    class="object-cover mb-8 w-full rounded-2xl xl:rounded-3xl aspect-video"
                  >
                </CardTilt>
                <List 
                customClass="px-6 py-5 bg-B3 rounded-2xl xl:rounded-3xl dark:bg-transparent dark:border dark:border-white"
                :items="[
                    { title: $t('project3.feedback.item1'), content: $t('project3.feedback.item1-1') },
                    { title: $t('project3.feedback.item2'), content: $t('project3.feedback.item2-1') }
                  ]"
                />
            </template>
          </Section3>
          <hr class="border-stone-300 dark:border-white/10">
          <!-- 下一個專案 -->
          <SectionNext 
          :title="$t('project1.core.title')"
          :linkTo="'/work/project1'"
          :icon="icon" 
          :showIcon="false"
          :text="$t('work.core.item5')" 
          :imgSrc="'https://i.imgur.com/8cDMtnX.png'"
          />
        </div>
        <Footer />
      </div>
    </div>

    <Modal :show="isModalOpen" @close="isModalOpen = false">
      <div class="w-full lg:aspect-video rounded-3xl max-h-[500px] object-cover object-center overflow-y-scroll overflow-hidden">
        <img
          class="object-cover object-center w-full"
          src="https://i.imgur.com/E3rF3z9.png"
          alt="Modal Image"
        />
      </div>
    </Modal>
  </template>
  
  <script>
  import { ref } from 'vue';
  import MingcuteEarth3Fill from '~icons/mingcute/earth-3-fill';
  
  export default {
  components: {
    MingcuteEarth3Fill,
  },
  setup() {
    const isModalOpen = ref(false);
    return { isModalOpen };
  },
  data() {
    return {
      icon: MingcuteEarth3Fill,
      sections: [
        { id: 'section1', name: 'work.title.item1' },
        { id: 'section2', name: 'work.title.item2' },
        { id: 'section3', name: 'work.title.item3' },
        // { id: 'section4', name: 'work.title.item4' },
        { id: 'section5', name: 'work.title.item5' },
        { id: 'section6', name: 'work.title.item6' },
        // { id: 'section7', name: 'work.title.item8' },
        { id: 'section8', name: 'work.title.item9' },
        { id: 'section9', name: 'work.title.item10' },
        { id: 'section11', name: 'work.title.item11' },
        { id: 'section12', name: 'work.title.item12' },
        { id: 'section14', name: 'work.title.item14' },
      ],
    };
  },
  
}
</script>
  