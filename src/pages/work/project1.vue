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
                  <div v-if="activeTab === 1">
                    <CardTilt @click="isModalOpen = true" class="cursor-pointer">
                      <img 
                        src="https://i.pinimg.com/1200x/af/cd/8f/afcd8f8ea177d6927da3ed1a8416da09.jpg"
                        alt="SiteMap"
                        class="object-cover w-full rounded-2xl xl:rounded-3xl"
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
                  :buttons="['project1.mockup.item1', 'project1.mockup.item2', 'project1.mockup.item3', 'project1.mockup.item4', 'project1.mockup.item5', 'project1.mockup.item6', 'project1.mockup.item7', 'project1.mockup.item7']">
                    <!-- Tab Contents -->
                    <template #default="{ activeTab }">
                      <div v-if="activeTab === 1" class="relative xl:px-12 lg:px-48">
                        <img 
                          src="https://i.pinimg.com/1200x/34/da/64/34da6401989b7f7dc27c2dee52f1e1a3.jpg"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                        >
                        <div class="hidden absolute top-1/4 xl:-right-44 lg:-right-6 lg:block">
                          <HoverIconButton 
                          class=""
                          icon="💡"
                          title="Tab 切換"
                          text="使用動態切換為不同表單，維持統一設計並減少額外開發，提供不同使用者註冊。"
                          />
                        </div>
                        <div class="hidden absolute top-1/2 xl:-right-44 lg:-right-6 lg:block">
                          <HoverIconButton 
                          class=""
                          icon="💡"
                          title="即時驗證"
                          text="使用動態切換為不同表單，維持統一設計並減少額外開發，提供不同使用者註冊。"
                          />
                        </div>
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

    <Modal :show="isModalOpen" @close="isModalOpen = false">
      <div class="w-full aspect-video rounded-3xl h-[500px] object-cover object-center overflow-y-scroll overflow-hidden">
        <img
          class="object-cover object-center w-full"
          src="https://i.pinimg.com/1200x/af/cd/8f/afcd8f8ea177d6927da3ed1a8416da09.jpg"
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
  