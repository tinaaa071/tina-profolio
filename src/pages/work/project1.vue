<template> 
     <div class="relative pb-6 text-sm sm:pb-10 bg-B4 dark:bg-stone-900 text-stone-800 xs:text-base dark:text-white">
      <Navbar />
      <ProgressBar />
      <BackToTop class="z-20" />
      <!-- Banner -->
      <Banner 
        title="123"
        bannerSrc="https://images.unsplash.com/photo-1688297969982-2d46e66ba2f2?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
      />
      <!-- Content -->
      <div class="absolute left-0 sm:top-[480px] top-[400px] w-full ">
        <!-- Info -->
        <Info 
        :title="$t('project1.core.title')"
        :info1="'2023.10 - 2024.10'"
        :info2="$t('project1.info.item3')"
        :info3="'UX 研究、設計系統、UI & Prototype 設計'"
        :info4="$t('project1.info.item1')"
        :tag="[$t('project1.info.item2'), $t('work.core.item3'), $t('project1.info.item4')]" 
        :iconsVisible="[true, false, true, true, false]"
        :linkTo="'/'"
        :icon="icon" 
        
        />
        <!-- Main Content -->
        <div>
          <ScrollSpy :sections="sections" />
          <!-- 專案資訊 -->
          <Section1
          id="section1"
          :info1="$t('project1.info.item1')"
          :info2="[$t('project1.info.item2'), $t('project1.info.item3'), $t('project1.info.item4')]"
          :info3="[$t('project1.info.item2'), $t('project1.info.item3'), $t('project1.info.item4')]"
          :info4="[
            { avatarSrc: 'https://images.unsplash.com/photo-1724942462164-7c30f103d91c?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', job: $t('project1.info.item3'), name: 'John Doe' },
            { avatarSrc: 'https://images.unsplash.com/photo-1724748860101-589aa7ee8b29?q=80&w=2748&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', job: $t('project1.info.item5'), name: 'Jane Smith' }
          ]"
          :content="$t('work.core.item5')"
          bgImg="https://images.unsplash.com/photo-1723904187003-807a2f7c8311?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
          />
          <!-- 專案概覽 -->
          <Section2
            id="section2"
            :briefs="[
            { title: $t('work.title.item2-1'), content: $t('project1.briefCard.item1') },
            { title: $t('work.title.item2-2'), content: $t('project1.briefCard.item2') },
            { title: $t('work.title.item2-3'), content: $t('project1.briefCard.item3') },
            { title: $t('work.title.item2-4'), content: $t('project1.briefCard.item4') }
          ]"
          />
          <!-- 專案背景 -->
          <Section3
            id="section3"
            :title="$t('work.title.item3')"
          >
            <template #content>
              <div>
                <p class="mb-6 font-normal">
                  {{ $t('project1.briefCard.item1') }}
                </p>
                <!-- <CardTilt>
                  <img 
                  src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                  class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                >
                </CardTilt> -->
                <Parallax
                backgroundImage="https://images.unsplash.com/photo-1731141028975-3eb6b91cef4c?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                speed="0.08"
                customClass="rounded-2xl xl:rounded-3xl aspect-video"
              />
              </div>
            </template>
          </Section3>
          <!-- 設計流程 -->
          <section id="section4" >
            <Parallax 
            class="h-96"
            backgroundImage="https://images.unsplash.com/photo-1731141028975-3eb6b91cef4c?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            />
          </section>
          <!-- 專案目標 -->
          <Section3
            id="section5"
            :title="$t('work.title.item5')"
          >
            <template #content>
              <StackCard>
                <template #card0>
                  <div>
                    <p class="mb-3 font-semibold text-white sm:mb-6 sm:text-xl dark:text-stone-900">
                      {{ $t('work.title.item5-1') }}
                    </p>
                    <p class="mb-1 text-sm font-semibold sm:mb-3 text-B1 sm:text-base">
                      {{ $t('work.title.item5-1') }}
                    </p>
                    <p class="text-sm font-normal text-B1">
                      {{ $t('work.title.item5-1') }}
                    </p>
                  </div>
                </template>
                <template #card1>
                  <div class="mb-6">
                    <p class="mb-3 font-semibold sm:mb-6 sm:text-xl text-stone-900 dark:text-white">
                      {{ $t('work.title.item5-2') }}
                    </p>
                    <p class="mb-1 text-sm font-semibold sm:mb-3 sm:text-base text-B1 dark:text-stone-400">
                      {{ $t('work.title.item5-1') }}
                    </p>
                    <p class="text-sm font-normal text-B1 dark:text-stone-400">
                      {{ $t('work.title.item5-1') }}
                    </p>
                  </div>
                  <CardTilt>
                    <img 
                    src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                    class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                  >
                  </CardTilt>
                </template>
              </StackCard>
            </template>
          </Section3>
          <!-- 前期研究 -->
          <Section3
            id="section6"
            :title="$t('work.title.item6')"
          >
            <template #content>
              <SurveyCard />
            </template>
          </Section3>
          <!-- 設計產出 -->
          <Section3
            id="section10"
            :title="$t('work.title.item10')"
          >
            <template #content>
              <div class="grid overflow-hidden grid-cols-1 rounded-2xl divide-y drop-shadow xl:rounded-3xl dark:border dark:border-white dark:divide-white divide-B2">
                <!-- Color -->
                <Accordion
                :title="$t('work.designSystem.item1')"
                >
                  <CardTilt>
                    <img 
                    src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                    class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                  >
                  </CardTilt>
                </Accordion>
                <!-- Typography -->
                <Accordion
                :title="$t('work.designSystem.item2')"
                >
                  <CardTilt>
                    <img 
                    src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                    class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                  >
                  </CardTilt>
                </Accordion>
              </div>
            </template>  
          </Section3>
          <hr class="border-stone-300 dark:border-white/20">
          <!-- 下一個專案 -->
          <SectionNext 
          :title="$t('project2.core.title')"
          :linkTo="'/'"
          :icon="icon" 
          :showIcon="false"
          :text="$t('work.core.item5')" 
          />
        </div>
        <Footer />
      </div>
    </div>
  </template>
  
  <script>
  import MingcuteEarth3Fill from '~icons/mingcute/earth-3-fill';
  
  export default {
  components: {
    MingcuteEarth3Fill,
  },
  data() {
    return {
      icon: MingcuteEarth3Fill, 
      sections: [
        { id: 'section1', name: 'work.title.item1' },
        { id: 'section2', name: 'work.title.item2' },
        { id: 'section3', name: 'work.title.item3' },
        { id: 'section4', name: 'work.title.item4' },
        { id: 'section5', name: 'work.title.item5' },
        { id: 'section6', name: 'work.title.item6' },
        { id: 'section10', name: 'work.title.item10' },
      ],
    };
  },
  
}

  </script>
  