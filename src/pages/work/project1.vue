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
        :info2="$t('project1.info.item2')"
        :info3="$t('project1.info.item3')"
        :info4="$t('project1.info.item1')"
        :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3')]" 
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
          :info2="[$t('project1.demand.item1'), $t('project1.demand.item2'), $t('project1.demand.item3'), $t('project1.demand.item4'), $t('project1.demand.item5'), $t('project1.demand.item6')]"
          :info4="[
            { avatarSrc: 'https://images.unsplash.com/photo-1724942462164-7c30f103d91c?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', job: $t('project1.team.item1'), name: 'Tina Chen' },
            { avatarSrc: 'https://images.unsplash.com/photo-1724748860101-589aa7ee8b29?q=80&w=2748&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', job: $t('project1.team.item4'), name: 'Freda Lin' },
            { avatarSrc: 'https://images.unsplash.com/photo-1724748860101-589aa7ee8b29?q=80&w=2748&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', job: $t('project1.team.item5'), name: 'Miwa Huang' },
            { avatarSrc: 'https://images.unsplash.com/photo-1724748860101-589aa7ee8b29?q=80&w=2748&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', job: $t('project1.team.item2'), name: 'William Chou' },
            { avatarSrc: 'https://images.unsplash.com/photo-1724748860101-589aa7ee8b29?q=80&w=2748&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', job: $t('project1.team.item3'), name: 'Jay Huang' },
            { avatarSrc: 'https://images.unsplash.com/photo-1724748860101-589aa7ee8b29?q=80&w=2748&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', job: $t('project1.team.item3'), name: 'David Huang' }
          ]"
          :content="$t('project1.brief.item1')"
          bgImg="https://images.unsplash.com/photo-1723904187003-807a2f7c8311?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
          >
            <ul class="leading-loose list-disc list-inside">
              <li>
                <span class="font-semibold">
                  {{ $t('project1.brief.item2') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project1.brief.item2-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project1.brief.item3') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project1.brief.item3-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project1.brief.item4') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project1.brief.item4-1') }}
                </span>
              </li>
            </ul>
          </Section1>
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
                  {{ $t('project1.background.item1') }}
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
                :cards="[1]"
                :cardColors="['bg-B3 dark:bg-stone-700']"
                :scrollEndOffset="700"
              >
                <template #card0>
                  <div class="dark:text-white text-stone-900">
                    <p class="mb-4 font-semibold md:mb-6 sm:mb-8 md:text-xl">
                      {{ $t('work.title.item5-2') }}
                    </p>
                    <List 
                    :items="[
                        { title: $t('project1.problem.item1') },
                        { title: $t('project1.problem.item2') },
                        { title: $t('project1.problem.item3') },
                        { title: $t('project1.problem.item4') },
                        { title: $t('project1.problem.item5') },
                        { title: $t('project1.problem.item6') }
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
                        { title: $t('project1.sa.item1') },
                        { title: $t('project1.sa.item2') },
                        { title: $t('project1.sa.item3') },
                        { title: $t('project1.sa.item4') },
                        { title: $t('project1.sa.item5') },
                      ]"
                    />
                  </div>
                  <div v-if="activeTab === 2">
                    <Ta
                      :cards="[
                        { avatarSrc: 'https://images.unsplash.com/photo-1527613426441-4da17471b66d?q=80&w=2904&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', title: $t('project1.ta.item1'), content: $t('project1.ta.item1-1') },
                        { avatarSrc: 'https://images.unsplash.com/photo-1609188076864-c35269136b09?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D', title: $t('project1.ta.item2'), content: $t('project1.ta.item2-1') }
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
          <EnlargeImg class="mx-auto" imageUrl="https://images.unsplash.com/photo-1731141028854-ed2dc691a6a2?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDl8fHxlbnwwfHx8fHw%3D" />
          <!-- 定義問題 -->
          <Section3
            id="section7"
            :title="$t('work.title.item8')"
          >
            <template #content-1>
              <!-- How Might We? -->
              <HMW>
                <ul class="leading-loose list-disc list-inside">
                    <li v-for="(item, index) in [$t('project1.research.item1'), $t('project1.research.item2'), $t('project1.research.item3'), $t('project1.research.item4'), $t('project1.research.item5'), $t('project1.research.item6')]" :key="index">
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
                        { title: $t('project1.hypo.item1'), content: $t('project1.hypo.item1-1') },
                        { title: $t('project1.hypo.item2'), content: $t('project1.hypo.item2-1') },
                        { title: $t('project1.hypo.item3'), content: $t('project1.hypo.item3-1') },
                        { title: $t('project1.hypo.item4'), content: $t('project1.hypo.item4-1') },
                        { title: $t('project1.hypo.item5'), content: $t('project1.hypo.item5-1') },
                        { title: $t('project1.hypo.item6'), content: $t('project1.hypo.item6-1') }
                      ]"
                    />
                  </div>
                  <div v-if="activeTab === 2">
                    <List 
                    :items="[
                        { title: $t('project1.challenge.item1'), content: $t('project1.challenge.item1-1') },
                        { title: $t('project1.challenge.item2'), content: $t('project1.challenge.item2-1') },
                        { title: $t('project1.challenge.item3'), content: $t('project1.challenge.item3-1') },
                        { title: $t('project1.challenge.item4'), content: $t('project1.challenge.item4-1') },
                        { title: $t('project1.challenge.item5'), content: $t('project1.challenge.item5-1') },
                        { title: $t('project1.challenge.item6'), content: $t('project1.challenge.item6-1') }
                      ]"
                    />
                  </div>
                </template>
              </TabCard>
            </template>
          </Section3>
          <!-- 設計發想 -->
          <Section3
            id="section8"
            :title="$t('work.title.item9')"
          >
            <template #content-1>
              <TabCard :buttons="['work.title.item9-2', 'work.title.item9-3']">
                <!-- Background Images -->
                <template #backgrounds>
                  <img src="https://images.unsplash.com/photo-1434030216411-0b793f4b4173?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://images.unsplash.com/photo-1505751172876-fa1923c5c528?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <!-- Sitemap -->
                  <div v-if="activeTab === 1">
                    <CardTilt @click="isModalOpen = true" class="cursor-pointer">
                      <img 
                        src="https://i.imgur.com/E3rF3z9.png"
                        alt="SiteMap"
                        class="object-cover w-full rounded-xl"
                      >
                    </CardTilt>
                  </div>
                  <div v-if="activeTab === 2">
                    <List 
                    :items="[
                        { title: $t('project1.challenge.item1'), content: $t('project1.challenge.item1-1') },
                        { title: $t('project1.challenge.item2'), content: $t('project1.challenge.item2-1') },
                        { title: $t('project1.challenge.item3'), content: $t('project1.challenge.item3-1') },
                        { title: $t('project1.challenge.item4'), content: $t('project1.challenge.item4-1') },
                        { title: $t('project1.challenge.item5'), content: $t('project1.challenge.item5-1') },
                        { title: $t('project1.challenge.item6'), content: $t('project1.challenge.item6-1') }
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
                    { title: $t('project1.principle.item1'), content: $t('project1.principle.item1-1') },
                    { title: $t('project1.principle.item2'), content: $t('project1.principle.item2-1') },
                    { title: $t('project1.principle.item3'), content: $t('project1.principle.item3-1') },
                    { title: $t('project1.principle.item4'), content: $t('project1.principle.item4-1') }
                  ]"
                />
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
                  :scrollableClass="'overflow-x-auto whitespace-nowrap'"
                  :buttonClass="'w-1/2'"
                  :buttons="['project1.mockup.tab.item1', 'project1.mockup.tab.item2', 'project1.mockup.tab.item3', 'project1.mockup.tab.item4', 'project1.mockup.tab.item5', 'project1.mockup.tab.item6', 'project1.mockup.tab.item7', 'project1.mockup.tab.item8', 'project1.mockup.tab.item9']">
                    <!-- Tab Contents -->
                    <template #default="{ activeTab }">
                      <div v-if="activeTab === 1" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/uxyQ8VJ.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute -right-56 top-1/4 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item1')"
                            :text="$t('project1.mockup.info.item1-1')"
                            />
                          </div>
                          <div class="hidden absolute -right-56 top-1/2 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item2')"
                            :text="$t('project1.mockup.info.item2-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 2" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/gJ53mCl.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item3')"
                            :text="$t('project1.mockup.info.item3-1')"
                            />
                          </div>
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item4')"
                            :text="$t('project1.mockup.info.item4-1')"
                            />
                          </div>
                          <div class="hidden absolute -right-56 top-1/2 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item5')"
                            :text="$t('project1.mockup.info.item5-1')"
                            />
                          </div>
                          <div class="hidden absolute top-[70%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item6')"
                            :text="$t('project1.mockup.info.item6-1')"
                            />
                          </div>
                          <div class="hidden absolute top-[80%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item7')"
                            :text="$t('project1.mockup.info.item7-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 3" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/0riUTFr.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute -right-56 top-1/3 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item8')"
                            :text="$t('project1.mockup.info.item8-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 4" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/gc0Hdez.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[12%] -left-56 lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project1.mockup.info.item9')"
                            :text="$t('project1.mockup.info.item9-1')"
                            />
                          </div>
                          <div class="hidden absolute -right-56 top-1/4 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item10')"
                            :text="$t('project1.mockup.info.item10-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 5" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/0FHQJ7D.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[5%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item11')"
                            :text="$t('project1.mockup.info.item11-1')"
                            />
                          </div>
                          <div class="hidden absolute top-[10%] -left-56 lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project1.mockup.info.item12')"
                            :text="$t('project1.mockup.info.item12-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 6" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/4lT873l.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item13')"
                            :text="$t('project1.mockup.info.item13-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[40%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project1.mockup.info.item14')"
                            :text="$t('project1.mockup.info.item14-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/58QRnM4.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item15')"
                            :text="$t('project1.mockup.info.item15-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 7" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/CMoGLpZ.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item16')"
                            :text="$t('project1.mockup.info.item16-1')"
                            />
                          </div>
                          <div class="hidden absolute top-[20%] -left-56 lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project1.mockup.info.item17')"
                            :text="$t('project1.mockup.info.item17-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 8" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/dwTOBeF.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item18')"
                            :text="$t('project1.mockup.info.item18-1')"
                            />
                          </div>
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item19')"
                            :text="$t('project1.mockup.info.item19-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/601998J.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item20')"
                            :text="$t('project1.mockup.info.item20-1')"
                            />
                          </div>
                          <div class="hidden absolute -right-56 top-1/2 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item21')"
                            :text="$t('project1.mockup.info.item21-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 9" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/N5gqmnY.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item22')"
                            :text="$t('project1.mockup.info.item22-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/2KNev1D.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute -right-56 top-1/2 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project1.mockup.info.item23')"
                            :text="$t('project1.mockup.info.item23-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 12">
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
                  <div class="pb-6 xs:pb-12 lg:pb-16">
                    <div class="flex relative justify-center items-center w-full h-full">
                      <!-- 影片B，寬度90%，保持比例縮放 -->
                      <Video
                        videoSrc="https://www.youtube.com/embed/_6jO-zrU5Do?autoplay=1&mute=1&loop=1"
                        class="absolute top-1 sm:top-2 left-0 w-[76%] sm:w-[64%] xl:w-[77%] object-contain"
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
        { id: 'section4', name: 'work.title.item4' },
        { id: 'section5', name: 'work.title.item5' },
        { id: 'section6', name: 'work.title.item6' },
        { id: 'section7', name: 'work.title.item8' },
        { id: 'section8', name: 'work.title.item9' },
        { id: 'section9', name: 'work.title.item10' },
        { id: 'section11', name: 'work.title.item11' },
        { id: 'section12', name: 'work.title.item12' },
        { id: 'section13', name: 'work.title.item13' },
        { id: 'section14', name: 'work.title.item14' },
      ],
    };
  },
  
}
</script>
  