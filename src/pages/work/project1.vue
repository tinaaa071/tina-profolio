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
      <div class="absolute left-0 sm:top-[480px] top-[400px] w-full leading-relaxed">
        <!-- Info -->
        <Info 
        :title="$t('project1.core.title')"
        :info1="'2023.10 - 2024.11'"
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
            <template #content-1>
              <StackCard
                :cards="[1, 2]"
                :cardColors="['bg-stone-900 dark:bg-B3', 'bg-B3 dark:bg-stone-700']"
                :scrollEndOffset="700"
              >
                <template #card0>
                  <div>
                    <p class="mb-2 font-semibold text-white md:mb-3 sm:mb-6 md:text-xl dark:text-stone-900">
                      {{ $t('work.title.item5-1') }}
                    </p>
                    <p class="mb-1 text-sm font-semibold sm:mb-3 md:text-base text-B1 sm:text-base">
                      {{ $t('work.title.item5-1') }}
                    </p>
                    <p class="text-sm font-normal text-B1">
                      {{ $t('work.title.item5-1') }}
                    </p>
                  </div>
                </template>
                <template #card1>
                  <div class="mb-6">
                    <p class="mb-2 font-semibold md:mb-3 sm:mb-6 md:text-xl text-stone-900 dark:text-white">
                      {{ $t('work.title.item5-2') }}
                    </p>
                    <p class="mb-1 text-sm font-semibold sm:mb-3 md:text-base text-B1 dark:text-stone-400">
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
            <template #content-1>
              <!-- How Might We? -->
              <HMW 
              text="我們如何協助居住在北北基桃且家中有學齡前孩童的家長，可以找到具有充足與透明的場地資訊及心得的親子活動，提升規劃效率？"
              />
              <TabCard :buttons="['work.title.item6-1', 'work.title.item6-2', 'work.title.item6-3']">
                <!-- Background Images -->
                <template #backgrounds>
                  <img src="https://images.unsplash.com/photo-1731141028975-3eb6b91cef4c?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://media.istockphoto.com/id/1043898904/photo/cobblestone-street-stockhom-sweden.webp?a=1&s=612x612&w=0&k=20&c=T51JUb6d8n9Vw56FPhM8SoC0YE5WhMiZL7O883d7mUc=" />
                  <img src="https://images.unsplash.com/photo-1731141707768-76d857b0f82d?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDd8fHxlbnwwfHx8fHw%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <div v-if="activeTab === 1">
                    我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。
                  </div>
                  <div v-if="activeTab === 2">
                    <CardTilt>
                      <img 
                      src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                      class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                    >
                    </CardTilt>
                  </div>
                  <div v-if="activeTab === 3">
                    我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。
                  </div>
                </template>
              </TabCard>
              <EnlargeImg class="mx-auto" imageUrl="https://images.unsplash.com/photo-1731141028854-ed2dc691a6a2?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDl8fHxlbnwwfHx8fHw%3D" />
            </template>
          </Section3>
          <!-- 設計產出 -->
          <Section3
            id="section11"
            :title="$t('work.title.item11')"
          >
            <!-- Design System -->
            <template #content-1>
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
            <!-- Mockup -->
            <template #content-2>
              <div class="bg-B5 dark:bg-stone-700">
                <TabCard 
                  class="p-6 border-none xl:px-56 md:px-10 md:py-8"
                  :customClass="[bg-transparent, p-0]"
                  :buttons="['work.title.item6-1', 'work.title.item6-2', 'work.title.item6-3']">
                    <!-- Tab Contents -->
                    <template #default="{ activeTab }">
                      <div v-if="activeTab === 1">
                        我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。
                      </div>
                      <div v-if="activeTab === 2" class="relative xl:px-12 lg:px-48">
                        <CardTilt>
                          <img 
                          src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl aspect-video"
                        >
                        </CardTilt>
                        <div class="hidden absolute top-2/3 xl:-right-44 lg:-right-6 lg:block">
                          <HoverIconButton 
                          class=""
                          icon="💡"
                          title="Work From Home"
                          text="我們針對周遭人們 Work From Home 之後我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。"
                          />
                        </div>
                      </div>
                      <div v-if="activeTab === 3">
                        <ImageCompare
                          beforeImage="https://images.unsplash.com/photo-1731141028975-3eb6b91cef4c?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                          afterImage="https://images.unsplash.com/photo-1731141295615-d09e4496c489?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDZ8fHxlbnwwfHx8fHw%3D"
                          :height="'h-96'"
                        />
                      </div>
                    </template>
                </TabCard>
              </div>
            </template>
            <!-- Prototype -->
            <template #content-3>
              <div class="bg-B3 dark:bg-stone-600">
                <div class="p-6 border-none xl:px-56 md:px-10 md:py-8">
                  <div class="xl:px-12 lg:px-48">
                    <CardTilt>
                      <img 
                      src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                      class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl aspect-video"
                    >
                    </CardTilt>
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
              <TabCard :buttons="['work.title.item6-1', 'work.title.item6-2', 'work.title.item6-3']">
                <!-- Background Images -->
                <template #backgrounds>
                  <img src="https://images.unsplash.com/photo-1731141028975-3eb6b91cef4c?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://media.istockphoto.com/id/1043898904/photo/cobblestone-street-stockhom-sweden.webp?a=1&s=612x612&w=0&k=20&c=T51JUb6d8n9Vw56FPhM8SoC0YE5WhMiZL7O883d7mUc=" />
                  <img src="https://images.unsplash.com/photo-1731141707768-76d857b0f82d?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDd8fHxlbnwwfHx8fHw%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <div v-if="activeTab === 1">
                    我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。
                  </div>
                  <div v-if="activeTab === 2">
                    <CardTilt>
                      <img 
                      src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                      class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                    >
                    </CardTilt>
                  </div>
                  <div v-if="activeTab === 3">
                    我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。
                  </div>
                </template>
              </TabCard>
            </template>
          </Section3>
          <!-- 易用性測試 -->
          <Section3
            id="section13"
            :title="$t('work.title.item13')"
          >
            <template #content-1>
              <TabCard :buttons="['work.title.item6-1', 'work.title.item6-2', 'work.title.item6-3']">
                <!-- Background Images -->
                <template #backgrounds>
                  <img src="https://images.unsplash.com/photo-1731141028975-3eb6b91cef4c?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://media.istockphoto.com/id/1043898904/photo/cobblestone-street-stockhom-sweden.webp?a=1&s=612x612&w=0&k=20&c=T51JUb6d8n9Vw56FPhM8SoC0YE5WhMiZL7O883d7mUc=" />
                  <img src="https://images.unsplash.com/photo-1731141707768-76d857b0f82d?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDd8fHxlbnwwfHx8fHw%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <div v-if="activeTab === 1">
                    我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。
                  </div>
                  <div v-if="activeTab === 2">
                    <CardTilt>
                      <img 
                      src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                      class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                    >
                    </CardTilt>
                  </div>
                  <div v-if="activeTab === 3">
                    我們針對周遭人們 Work From Home 之後，生活習慣與心態上的轉變去做潛在使用者的樣貌的發想。
                  </div>
                </template>
              </TabCard>
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
                    src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                    class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                  >
                </CardTilt>
            </template>
          </Section3>
          <hr class="border-stone-300 dark:border-white/10">
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
        { id: 'section11', name: 'work.title.item11' },
        { id: 'section12', name: 'work.title.item12' },
        { id: 'section13', name: 'work.title.item13' },
        { id: 'section14', name: 'work.title.item14' },
      ],
    };
  },
  
}

  </script>
  