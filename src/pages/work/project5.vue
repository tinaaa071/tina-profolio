<template> 
     <div class="relative pb-6 text-sm sm:pb-10 bg-B4 dark:bg-stone-900 text-stone-800 xs:text-base dark:text-white">
      <Navbar />
      <ProgressBar />
      <BackToTop class="z-20" />
      <!-- Banner -->
      <Banner 
        bannerSrc="https://i.imgur.com/0AOKRdk.png"
      />
      <!-- Content -->
      <div class="absolute left-0 sm:top-[480px] top-[400px] w-full leading-relaxed">
        <!-- Info -->
        <Info 
        :title="$t('project5.core.title')"
        :info1="'2023.06 - 2023.08'"
        :info2="[$t('project5.team.item1')]" 
        :info3="$t('project5.info.item3')"
        :info4="$t('project5.info.item1')"
        :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item4'), $t('projectTag.item6')]" 
        :iconsVisible="[true, false, false, false, false, true, true, false, false]"
        :linkTo="'/'"
        :icon="icon" 
        :showBTN="false"
        />
        <!-- Main Content -->
        <div>
          <ScrollSpy :sections="sections" />
          <!-- 專案資訊 -->
          <Section1
          id="section1"
          :info1="$t('project5.info.item1')"
          :info2="[$t('project5.demand.item1'), $t('project5.demand.item2'), $t('project5.demand.item3'), $t('project5.demand.item4'), $t('project5.demand.item5'), $t('project5.demand.item6'), $t('project5.demand.item7'), $t('project5.demand.item8')]"
          :info4="[
            { avatarSrc: 'https://i.imgur.com/93zadWo.png', job: $t('project5.team.item1'), name: 'Tina Chen' },
            { avatarSrc: 'https://i.imgur.com/lL2Vk89.png', job: $t('project5.team.item4'), name: 'Winnie Lin' },
            { avatarSrc: 'https://i.imgur.com/fBGnJUp.png', job: $t('project5.team.item6'), name: 'Lotus Chiu' }
          ]"
          :content="$t('project5.brief.item1')"
          bannerSrc="https://i.imgur.com/GjH2I79.png"
          >
            <ul class="leading-loose list-disc list-inside">
              <li>
                <span class="font-semibold">
                  {{ $t('project5.brief.item2') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project5.brief.item2-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project5.brief.item3') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project5.brief.item3-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project5.brief.item4') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project5.brief.item4-1') }}
                </span>
              </li>
            </ul>
          </Section1>
          <!-- 專案概覽 -->
          <Section2
            id="section2"
            :briefs="[
            { title: $t('work.title.item2-1'), content: $t('project5.briefCard.item1') },
            { title: $t('work.title.item2-2'), content: $t('project5.briefCard.item2') },
            { title: $t('work.title.item2-3'), content: $t('project5.briefCard.item3') },
            { title: $t('work.title.item2-4'), content: $t('project5.briefCard.item4') }
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
                <p class="mb-6 font-normal text-justify">
                  {{ $t('project5.background.item1') }}
                </p>
                <CardTilt>
                  <img 
                  src="https://www.taichung.gov.tw/media/390358/%E6%96%B0%E8%81%9E%E7%A8%BF%E6%90%AD%E9%85%8D%E7%85%A7%E7%89%87.jpg"
                  class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                >
                </CardTilt>
                <!-- <Parallax
                backgroundImage="https://www.taichung.gov.tw/media/390358/%E6%96%B0%E8%81%9E%E7%A8%BF%E6%90%AD%E9%85%8D%E7%85%A7%E7%89%87.jpg"
                speed="0.08"
                customClass="rounded-2xl xl:rounded-3xl aspect-video sm:bg-contain bg-cover"
              /> -->
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
                        { title: $t('project5.goal.item1') },
                        { title: $t('project5.goal.item2') },
                        { title: $t('project5.goal.item3') },
                        { title: $t('project5.goal.item4') },
                        { title: $t('project5.goal.item5') }
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
                        { title: $t('project5.problem.item1') },
                        { title: $t('project5.problem.item2') },
                        { title: $t('project5.problem.item3') },
                        { title: $t('project5.problem.item4') },
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
                        { title: $t('project5.sa.item1') },
                        { title: $t('project5.sa.item2') },
                        { title: $t('project5.sa.item3') },
                        { title: $t('project5.sa.item4') }
                      ]"
                    />
                  </div>
                  <div v-if="activeTab === 2">
                    <Ta
                      :cards="[
                        { avatarSrc: 'https://images.unsplash.com/photo-1526795443948-005b48ce4791?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', title: $t('project5.ta.item1'), content: $t('project5.ta.item1-1') },
                        { avatarSrc: 'https://cdn2.ettoday.net/images/3058/d3058145.jpg', title: $t('project5.ta.item2'), content: $t('project5.ta.item2-1') }
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
          <EnlargeImg class="mx-auto" imageUrl="https://images.unsplash.com/photo-1559234938-b60fff04894d?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
          <!-- 定義問題 -->
          <Section3
            id="section7"
            :title="$t('work.title.item8')"
          >
            <template #content-1>
              <!-- How Might We? -->
              <HMW>
                <ul class="leading-loose list-disc list-inside">
                    <li v-for="(item, index) in [$t('project5.research.item1'), $t('project5.research.item2'), $t('project5.research.item3'), $t('project5.research.item4')]" :key="index">
                      <span>{{ item }}</span>
                    </li>
                  </ul>
              </HMW>
              <TabCard :buttons="['work.title.item8-2', 'work.title.item8-3']">
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
                        { title: $t('project5.hypo.item1'), content: $t('project5.hypo.item1-1') },
                        { title: $t('project5.hypo.item2'), content: $t('project5.hypo.item2-1') },
                        { title: $t('project5.hypo.item3'), content: $t('project5.hypo.item3-1') },
                        { title: $t('project5.hypo.item4'), content: $t('project5.hypo.item4-1') }
                      ]"
                    />
                  </div>
                  <div v-if="activeTab === 2">
                    <List 
                    :items="[
                        { title: $t('project5.challenge.item1'), content: $t('project5.challenge.item1-1') },
                        { title: $t('project5.challenge.item2'), content: $t('project5.challenge.item2-1') },
                        { title: $t('project5.challenge.item3'), content: $t('project5.challenge.item3-1') }
                      ]"
                    />
                  </div>
                </template>
              </TabCard>
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
                    { title: $t('project5.principle.item1'), content: $t('project5.principle.item1-1') },
                    { title: $t('project5.principle.item2'), content: $t('project5.principle.item2-1') }
                  ]"
                />
            </template>
          </Section3>
          <!-- Banner -->
          <Parallax 
            class="md:h-[500px] h-64"
            backgroundImage="https://raw.githubusercontent.com/tinaaa071/video/main/project5.png"
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
                      src="https://i.imgur.com/1xNwgZi.png"
                      alt="Banner"
                      class="object-cover w-full mb-8 rounded-2xl xl:rounded-3xl aspect-video"
                    >
                </CardTilt>
                <p 
                v-html="$t('project5.system.item1')"
                class="text-justify"
                >
                </p>
              </div>
            </template>  
            <!-- Prototype -->
            <template #content-2>
              <div class="bg-B3 dark:bg-stone-600">
                <div class="p-6 space-y-16 border-none xl:px-56 md:px-10 md:py-8">
                  <!-- P1 -->
                  <div class="grid items-start justify-between grid-cols-1 gap-6 sm:gap-8 lg:gap-16 sm:grid-cols-4 sm:flex-row">
                    <!-- Content -->
                    <div class="sm:col-span-3">
                      <p class="mb-2 text-base font-semibold">
                        {{ $t('project5.prototype.item1') }}
                      </p>
                      <p class="text-base font-normal">
                        {{ $t('project5.prototype.item1-1') }}
                      </p>
                    </div>
                    <!-- Video -->
                    <div class="relative flex items-center justify-end">
                      <!-- 影片B，寬度90%，保持比例縮放 -->
                      <Video
                        videoSrc="https://i.imgur.com/sG8Dx6A.mp4"
                        class="top-0 sm:top-1 w-[48%] sm:w-[76%] xl:w-[96%] object-contain rounded-[24px] sm:rounded-3xl overflow-hidden mx-auto"
                        videoClass="aspect-[23/49]"
                      />
                      
                      <!-- 圖片A，寬度90%，保持比例縮放 -->
                      <img
                        ref="image"
                        src="https://i.imgur.com/G1u7QeQ.png"
                        alt="Image A"
                        class="object-contain absolute top-0 sm:w-[80%] xl:w-full w-1/2 left-1/2 -translate-x-1/2 transform"
                      />
                    </div>
                  </div>
                  <!-- P2 -->
                  <div class="grid items-start justify-between grid-cols-1 gap-6 sm:gap-8 lg:gap-16 sm:grid-cols-4 sm:flex-row">
                    <!-- Content -->
                    <div class="sm:col-span-3">
                      <p class="mb-2 text-base font-semibold">
                        {{ $t('project5.prototype.item2') }}
                      </p>
                      <p class="text-base font-normal">
                        {{ $t('project5.prototype.item2-1') }}
                      </p>
                    </div>
                    <!-- Video -->
                    <div class="relative flex items-center justify-end">
                      <!-- 影片B，寬度90%，保持比例縮放 -->
                      <Video
                        videoSrc="https://i.imgur.com/9mQJLEP.mp4"
                        class="top-0 sm:top-1 w-[48%] sm:w-[76%] xl:w-[96%] object-contain rounded-[24px] sm:rounded-3xl overflow-hidden mx-auto"
                        videoClass="aspect-[23/49]"
                      />
                      
                      <!-- 圖片A，寬度90%，保持比例縮放 -->
                      <img
                        ref="image"
                        src="https://i.imgur.com/G1u7QeQ.png"
                        alt="Image A"
                        class="object-contain absolute top-0 sm:w-[80%] xl:w-full w-1/2 left-1/2 -translate-x-1/2 transform"
                      />
                    </div>
                  </div>
                  <!-- P3 -->
                  <div class="grid items-start justify-between grid-cols-1 gap-6 sm:gap-8 lg:gap-16 sm:grid-cols-4 sm:flex-row">
                    <!-- Content -->
                    <div class="sm:col-span-3">
                      <p class="mb-2 text-base font-semibold">
                        {{ $t('project5.prototype.item3') }}
                      </p>
                      <p class="text-base font-normal">
                        {{ $t('project5.prototype.item3-1') }}
                      </p>
                    </div>
                    <!-- Video -->
                    <div class="relative flex items-center justify-end">
                      <!-- 影片B，寬度90%，保持比例縮放 -->
                      <Video
                        videoSrc="https://i.imgur.com/SAgKNwP.mp4"
                        class="top-0 sm:top-1 w-[48%] sm:w-[76%] xl:w-[96%] object-contain rounded-[24px] sm:rounded-3xl overflow-hidden mx-auto"
                        videoClass="aspect-[23/49]"
                      />
                      
                      <!-- 圖片A，寬度90%，保持比例縮放 -->
                      <img
                        ref="image"
                        src="https://i.imgur.com/G1u7QeQ.png"
                        alt="Image A"
                        class="object-contain absolute top-0 sm:w-[80%] xl:w-full w-1/2 left-1/2 -translate-x-1/2 transform"
                      />
                    </div>
                  </div>
                  <!-- P4 -->
                  <div class="grid items-start justify-between grid-cols-1 gap-6 sm:gap-8 lg:gap-16 sm:grid-cols-4 sm:flex-row">
                    <!-- Content -->
                    <div class="sm:col-span-3">
                      <p class="mb-2 text-base font-semibold">
                        {{ $t('project5.prototype.item4') }}
                      </p>
                      <p class="text-base font-normal">
                        {{ $t('project5.prototype.item4-1') }}
                      </p>
                    </div>
                    <!-- Video -->
                    <div class="relative flex items-center justify-end">
                      <!-- 影片B，寬度90%，保持比例縮放 -->
                      <Video
                        videoSrc="https://i.imgur.com/2I7qO0x.mp4"
                        class="top-0 sm:top-1 w-[48%] sm:w-[76%] xl:w-[96%] object-contain rounded-[24px] sm:rounded-3xl overflow-hidden mx-auto"
                        videoClass="aspect-[23/49]"
                      />
                      
                      <!-- 圖片A，寬度90%，保持比例縮放 -->
                      <img
                        ref="image"
                        src="https://i.imgur.com/G1u7QeQ.png"
                        alt="Image A"
                        class="object-contain absolute top-0 sm:w-[80%] xl:w-full w-1/2 left-1/2 -translate-x-1/2 transform"
                      />
                    </div>
                  </div>
                  <!-- P5 -->
                  <div class="grid items-start justify-between grid-cols-1 gap-6 sm:gap-8 lg:gap-16 sm:grid-cols-4 sm:flex-row">
                    <!-- Content -->
                    <div class="sm:col-span-3">
                      <p class="mb-2 text-base font-semibold">
                        {{ $t('project5.prototype.item5') }}
                      </p>
                      <p class="text-base font-normal">
                        {{ $t('project5.prototype.item5-1') }}
                      </p>
                    </div>
                    <!-- Video -->
                    <div class="relative flex items-center justify-end">
                      <!-- 影片B，寬度90%，保持比例縮放 -->
                      <Video
                        videoSrc="https://i.imgur.com/2O8DlTl.mp4"
                        class="top-0 sm:top-1 w-[48%] sm:w-[76%] xl:w-[96%] object-contain rounded-[24px] sm:rounded-3xl overflow-hidden mx-auto"
                        videoClass="aspect-[23/49]"
                      />
                      
                      <!-- 圖片A，寬度90%，保持比例縮放 -->
                      <img
                        ref="image"
                        src="https://i.imgur.com/G1u7QeQ.png"
                        alt="Image A"
                        class="object-contain absolute top-0 sm:w-[80%] xl:w-full w-1/2 left-1/2 -translate-x-1/2 transform"
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
              <ImageCompare
                beforeImage="https://i.imgur.com/WuQTnYE.png"
                afterImage="https://i.imgur.com/JYuHwsK.png"
                heightClass="md:h-96 h-64"
                class="mb-8"
                :beforeText="$t('project5.handoff.item2-2')"
                :afterText="$t('project5.handoff.item2-1')"
              />
            <p v-html="$t('project5.handoff.item1')" class="font-normal"></p>
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
                    src="https://i.imgur.com/0AOKRdk.png"
                    class="object-cover w-full mb-8 rounded-2xl xl:rounded-3xl aspect-video"
                  >
                </CardTilt>
                <List 
                customClass="px-6 py-5 bg-B3 rounded-2xl xl:rounded-3xl dark:bg-transparent dark:border dark:border-white"
                :items="[
                    { title: $t('project5.feedback.item1'), content: $t('project5.feedback.item1-1') },
                    { title: $t('project5.feedback.item2'), content: $t('project5.feedback.item2-1') },
                    { title: $t('project5.feedback.item3'), content: $t('project5.feedback.item3-1') },
                    { title: $t('project5.feedback.item4'), content: $t('project5.feedback.item4-1') }
                  ]"
                />
            </template>
          </Section3>
          <hr class="border-stone-300 dark:border-white/10">
          <!-- 下一個專案 -->
          <SectionNext 
          :title="$t('project2.core.title')"
          :linkTo="'/work/project2'"
          :icon="icon" 
          :showIcon="false"
          :text="$t('work.core.item5')" 
          :imgSrc="'https://i.imgur.com/CrxmhKx.png'"
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
        { id: 'section7', name: 'work.title.item8' },
        // { id: 'section8', name: 'work.title.item9' },
        { id: 'section9', name: 'work.title.item10' },
        { id: 'section11', name: 'work.title.item11' },
        { id: 'section12', name: 'work.title.item12' },
        { id: 'section14', name: 'work.title.item14' },
      ],
    };
  },
  
}
</script>
  