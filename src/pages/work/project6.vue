<template> 
     <div class="relative pb-6 text-sm sm:pb-10 bg-B4 dark:bg-stone-900 text-stone-800 xs:text-base dark:text-white">
      <Navbar />
      <ProgressBar />
      <BackToTop class="z-20" />
      <!-- Banner -->
      <Banner 
        bannerSrc="https://i.imgur.com/b1JyLC2.jpeg"
      />
      <!-- Content -->
      <div class="absolute left-0 sm:top-[480px] top-[400px] w-full leading-relaxed">
        <!-- Info -->
        <Info 
        :title="$t('project6.core.title')"
        :info1="'2023.05 - 2023.07'"
        :info2="[$t('project6.team.item1')]" 
        :info3="$t('project6.info.item3')"
        :info4="$t('project6.info.item1')"
        :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3'), $t('projectTag.item6')]" 
        :iconsVisible="[true, false, false, false, true, true, true, false, false]"
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
          :info1="$t('project6.info.item1')"
          :info2="[$t('project6.demand.item1'), $t('project6.demand.item2'), $t('project6.demand.item3'), $t('project6.demand.item4')]"
          :info4="[
            { avatarSrc: 'https://i.imgur.com/93zadWo.png', job: $t('project6.team.item1'), name: 'Tina Chen' },
            { avatarSrc: 'https://i.imgur.com/ZJwqurr.png', job: $t('project6.team.item5'), name: 'Rowena Hsu' },
            { avatarSrc: 'https://i.imgur.com/fBGnJUp.png', job: $t('project6.team.item2'), name: 'William Chou' },
            { avatarSrc: 'https://i.imgur.com/vEcl0rw.png', job: $t('project6.team.item3'), name: 'David Huang' }
          ]"
          :content="$t('project6.brief.item1')"
          bannerSrc="https://i.imgur.com/V2Agc1k.jpeg"
          >
            <ul class="leading-loose list-disc list-inside">
              <li>
                <span class="font-semibold">
                  {{ $t('project6.brief.item2') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project6.brief.item2-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project6.brief.item3') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project6.brief.item3-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project6.brief.item4') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project6.brief.item4-1') }}
                </span>
              </li>
            </ul>
          </Section1>
          <!-- 專案概覽 -->
          <Section2
            id="section2"
            :briefs="[
            { title: $t('work.title.item2-1'), content: $t('project6.briefCard.item1') },
            { title: $t('work.title.item2-2'), content: $t('project6.briefCard.item2') },
            { title: $t('work.title.item2-3'), content: $t('project6.briefCard.item3') },
            { title: $t('work.title.item2-4'), content: $t('project6.briefCard.item4') }
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
                  {{ $t('project6.background.item1') }}
                </p>
                <Parallax
                backgroundImage="https://i.imgur.com/7LTx0AW.png"
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
                        { title: $t('project6.goal.item1') },
                        { title: $t('project6.goal.item2') },
                        { title: $t('project6.goal.item3') },
                        { title: $t('project6.goal.item4') },
                        { title: $t('project6.goal.item5') },
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
                        { title: $t('project6.problem.item1') },
                        { title: $t('project6.problem.item2') },
                        { title: $t('project6.problem.item3') },
                        { title: $t('project6.problem.item4') },
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
                  <img src="https://images.unsplash.com/photo-1681907285194-20d95866eb6e?q=80&w=2832&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://images.unsplash.com/photo-1650611250959-1e823abf6841?q=80&w=2832&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <div v-if="activeTab === 1">
                    <List 
                    :items="[
                        { title: $t('project6.sa.item1') },
                        { title: $t('project6.sa.item2') },
                        { title: $t('project6.sa.item3') }
                      ]"
                    />
                  </div>
                  <div v-if="activeTab === 2">
                    <Ta
                      :cards="[
                        { avatarSrc: 'https://images.unsplash.com/photo-1576091358783-a212ec293ff3?q=80&w=3000&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', title: $t('project6.ta.item1'), content: $t('project6.ta.item1-1') }
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
          <EnlargeImg class="mx-auto" imageUrl="https://i.imgur.com/xfqOjF3.jpeg" />
          <!-- 設計發想 -->
          <Section3
            id="section8"
            :title="$t('work.title.item9')"
          >
            <template #content-1>
              <CardTilt @click="isModalOpen = true" class="cursor-pointer">
                <img 
                  src="https://i.imgur.com/wX6YVo4.png"
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
                    { title: $t('project6.principle.item1'), content: $t('project6.principle.item1-1') },
                    { title: $t('project6.principle.item2'), content: $t('project6.principle.item2-1') },
                    { title: $t('project6.principle.item3'), content: $t('project6.principle.item3-1') },
                    { title: $t('project6.principle.item4'), content: $t('project6.principle.item4-1') }
                  ]"
                />
            </template>
          </Section3>
          <!-- Banner -->
          <Parallax 
            class="md:h-[500px] h-64"
            backgroundImage="https://raw.githubusercontent.com/tinaaa071/video/main/project6.png"
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
                      src="https://i.imgur.com/KZUEX0t.png"
                      alt="Banner"
                      class="object-cover w-full mb-8 rounded-2xl xl:rounded-3xl aspect-video"
                    >
                </CardTilt>
                <p 
                v-html="$t('project6.system.item1')"
                class="text-justify"
                >
                </p>
                <br>
                <ListNum :items="[
                  {title: $t('project6.system.item2'), description:  $t('project6.system.item2-1')},
                  {title: $t('project6.system.item3'), description:  $t('project6.system.item3-1')},
                  {title: $t('project6.system.item4'), description:  $t('project6.system.item4-1')}
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
                  :buttons="['project6.mockup.tab.item1', 'project6.mockup.tab.item2', 'project6.mockup.tab.item3', 'project6.mockup.tab.item4', 'project6.mockup.tab.item5', 'project6.mockup.tab.item6', 'project6.mockup.tab.item7']">
                    <!-- Tab Contents -->
                    <template #default="{ activeTab }">
                      <div v-if="activeTab === 1" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/mQ7GkMF.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="absolute hidden -right-56 top-1/4 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item1')"
                            :text="$t('project6.mockup.info.item1-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 2" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/lwR4FYo.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute -left-56 top-[5%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project6.mockup.info.item2')"
                            :text="$t('project6.mockup.info.item2-1')"
                            />
                          </div>
                          <div class="absolute hidden -right-56 top-1/4 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item3')"
                            :text="$t('project6.mockup.info.item3-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 3" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/XOfspzv.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute -right-56 top-[10%] lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item4')"
                            :text="$t('project6.mockup.info.item4-1')"
                            />
                          </div>
                          <div class="absolute hidden -right-56 top-1/4 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item5')"
                            :text="$t('project6.mockup.info.item5-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 4" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/i0VNqK3.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[15%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item6')"
                            :text="$t('project6.mockup.info.item6-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[30%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project6.mockup.info.item7')"
                            :text="$t('project6.mockup.info.item7-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 5" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/Y3OUpOG.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[15%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item8')"
                            :text="$t('project6.mockup.info.item8-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[30%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project6.mockup.info.item9')"
                            :text="$t('project6.mockup.info.item9-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/KwtASiM.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[15%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item10')"
                            :text="$t('project6.mockup.info.item10-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[50%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project6.mockup.info.item11')"
                            :text="$t('project6.mockup.info.item11-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 6" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/Oe25I19.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item13')"
                            :text="$t('project6.mockup.info.item13-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[15%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project6.mockup.info.item12')"
                            :text="$t('project6.mockup.info.item12-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/B237ak2.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[15%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item14')"
                            :text="$t('project6.mockup.info.item14-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 7" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/bwqHGj3.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[50%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item15')"
                            :text="$t('project6.mockup.info.item15-1')"
                            />
                          </div>
                        </div>
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/3zaTvHg.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item16')"
                            :text="$t('project6.mockup.info.item16-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/akBi8wB.png"
                          class="object-cover w-full mx-auto rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[50%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project6.mockup.info.item17')"
                            :text="$t('project6.mockup.info.item17-1')"
                            />
                          </div>
                        </div>
                      </div>
                    </template>
                </TabCard>
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
                  src="https://i.imgur.com/9sDtGXD.png"
                  class="object-cover w-full mb-8 rounded-2xl xl:rounded-3xl aspect-video"
                >
              </CardTilt>
            <p v-html="$t('project6.handoff.item1')" class="font-normal"></p>
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
                    src="https://i.imgur.com/b1JyLC2.jpeg"
                    class="object-cover w-full mb-8 rounded-2xl xl:rounded-3xl aspect-video"
                  >
                </CardTilt>
                <List 
                customClass="px-6 py-5 bg-B3 rounded-2xl xl:rounded-3xl dark:bg-transparent dark:border dark:border-white"
                :items="[
                    { title: $t('project6.feedback.item1'), content: $t('project6.feedback.item1-1') },
                    { title: $t('project6.feedback.item2'), content: $t('project6.feedback.item2-1') }
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
      <div class="w-full  rounded-3xl max-h-[500px] object-cover object-center overflow-y-scroll overflow-hidden">
        <img
          class="object-cover object-center w-full"
          src="https://i.imgur.com/wX6YVo4.png"
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
  