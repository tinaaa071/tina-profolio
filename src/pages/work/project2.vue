<template> 
     <div class="relative pb-6 text-sm sm:pb-10 bg-B4 dark:bg-stone-900 text-stone-800 xs:text-base dark:text-white">
      <Navbar />
      <ProgressBar />
      <BackToTop class="z-20" />
      <!-- Banner -->
      <Banner 
        bannerSrc="https://i.imgur.com/xZ10FFb.png"
      />
      <!-- Content -->
      <div class="absolute left-0 sm:top-[480px] top-[400px] w-full leading-relaxed">
        <!-- Info -->
        <Info 
        :title="$t('project2.core.title')"
        :info1="$t('project2.info.item0')"
        :info2="[$t('project2.team.item1')]" 
        :info3="$t('project2.info.item3')"
        :info4="$t('project2.info.item1')"
        :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3'), $t('projectTag.item8')]" 
        :iconsVisible="[true, false, false, true, true, true, true, false, false]"
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
          :info1="$t('project2.info.item1')"
          :info2="[$t('project2.demand.item1'), $t('project2.demand.item2'), $t('project2.demand.item3'), $t('project2.demand.item4'), $t('project2.demand.item5'), $t('project2.demand.item6')]"
          :info4="[
            { avatarSrc: 'https://i.imgur.com/93zadWo.png', job: $t('project1.team.item1'), name: 'Tina Chen' },
            { avatarSrc: 'https://i.imgur.com/lL2Vk89.png', job: $t('project1.team.item4'), name: 'Freda Lin' },
            { avatarSrc: 'https://i.imgur.com/ZJwqurr.png', job: $t('project1.team.item5'), name: 'Miwa Huang' },
            { avatarSrc: 'https://i.imgur.com/fBGnJUp.png', job: $t('project1.team.item2'), name: 'William Chou' },
            { avatarSrc: 'https://i.imgur.com/eS6haTX.png', job: $t('project1.team.item3'), name: 'Jay Huang' },
            { avatarSrc: 'https://i.imgur.com/vEcl0rw.png', job: $t('project1.team.item3'), name: 'David Huang' }
          ]"
          :content="$t('project2.brief.item1')"
          bannerSrc="https://i.imgur.com/67mU1lV.png"
          >
            <ul class="leading-loose list-disc list-inside">
              <li>
                <span class="font-semibold">
                  {{ $t('project2.brief.item2') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project2.brief.item2-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project2.brief.item3') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project2.brief.item3-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project2.brief.item4') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project2.brief.item4-1') }}
                </span>
              </li>
            </ul>
          </Section1>
          <!-- 專案概覽 -->
          <Section2
            id="section2"
            :briefs="[
            { title: $t('work.title.item2-1'), content: $t('project2.briefCard.item1') },
            { title: $t('work.title.item2-2'), content: $t('project2.briefCard.item2') },
            { title: $t('work.title.item2-3'), content: $t('project2.briefCard.item3') },
            { title: $t('work.title.item2-4'), content: $t('project2.briefCard.item4') }
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
                  {{ $t('project2.background.item1') }}
                </p>
                  <!-- <CreditImg 
                    imgSrc="https://images.unsplash.com/photo-1492538368677-f6e0afe31dcc?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                    imgCredit="Credit: Unsplash"
                  /> -->
                  <Parallax
                backgroundImage="https://images.unsplash.com/photo-1492538368677-f6e0afe31dcc?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
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
            backgroundImage="https://images.unsplash.com/photo-1575654402689-8f45b1ee6179?q=80&w=2962&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
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
                        { title: $t('project1.goal.item1') },
                        { title: $t('project1.goal.item2') },
                        { title: $t('project1.goal.item3') }
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
                        { title: $t('project1.problem.item1') },
                        { title: $t('project1.problem.item2') },
                        { title: $t('project1.problem.item3') },
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
                        { title: $t('project2.sa.item1') },
                        { title: $t('project2.sa.item2') },
                        { title: $t('project2.sa.item3') },
                        { title: $t('project2.sa.item4') }
                      ]"
                    />
                  </div>
                  <div v-if="activeTab === 2">
                    <Ta
                      :cards="[
                        { avatarSrc: 'https://upload.wikimedia.org/wikipedia/commons/a/a3/ROC_Ministry_of_Health_and_Welfare_Seal.svg', title: $t('project2.ta.item1'), content: $t('project2.ta.item1-1') },
                        { avatarSrc: 'https://www.ntuh.gov.tw/ckfinder_file/OPD/images/2023/building_.jpg', title: $t('project2.ta.item2'), content: $t('project2.ta.item2-1') }
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
          <EnlargeImg class="mx-auto" imageUrl="https://images.unsplash.com/photo-1575654402689-8f45b1ee6179?q=80&w=2962&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
          <!-- 定義問題 -->
          <Section3
            id="section7"
            :title="$t('work.title.item8')"
          >
            <template #content-1>
              <!-- How Might We? -->
              <HMW>
                <ul class="leading-loose list-disc list-inside">
                    <li v-for="(item, index) in [$t('project2.research.item1'), $t('project2.research.item2'), $t('project2.research.item3'), $t('project2.research.item4'), $t('project2.research.item5')]" :key="index">
                      <span>{{ item }}</span>
                    </li>
                  </ul>
              </HMW>
              <TabCard :buttons="['work.title.item8-2', 'work.title.item8-3']">
                <!-- Background Images -->
                <template #backgrounds>
                  <img src="https://images.unsplash.com/photo-1471107340929-a87cd0f5b5f3?q=80&w=2746&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://images.unsplash.com/photo-1710228690874-c9f1b003b9ea?q=80&w=2671&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <div v-if="activeTab === 1">
                    <List 
                    :items="[
                        { title: $t('project2.hypo.item1'), content: $t('project2.hypo.item1-1') },
                        { title: $t('project2.hypo.item2'), content: $t('project2.hypo.item2-1') },
                        { title: $t('project2.hypo.item3'), content: $t('project2.hypo.item3-1') },
                        { title: $t('project2.hypo.item4'), content: $t('project2.hypo.item4-1') },
                        { title: $t('project2.hypo.item5'), content: $t('project2.hypo.item5-1') },
                        { title: $t('project2.hypo.item6'), content: $t('project2.hypo.item6-1') }
                      ]"
                    />
                  </div>
                  <div v-if="activeTab === 2">
                    <List 
                    :items="[
                        { title: $t('project2.challenge.item1'), content: $t('project2.challenge.item1-1') },
                        { title: $t('project2.challenge.item2'), content: $t('project2.challenge.item2-1') }
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
                  <img src="https://images.unsplash.com/photo-1460574283810-2aab119d8511?q=80&w=2663&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://images.unsplash.com/photo-1646617747563-4f080bddf282?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <!-- Sitemap -->
                  <div v-if="activeTab === 1">
                    <CardTilt @click="openModal('sitemap')" class="cursor-pointer">
                      <img 
                        src="https://i.imgur.com/BMLBzRf.png"
                        alt="SiteMap"
                        class="object-cover w-full rounded-xl"
                      >
                    </CardTilt>
                  </div>
                  <!-- User Flow -->
                  <div v-if="activeTab === 2">
                    <div class="space-y-6 sm:space-y-8">
                      <p v-html="$t('project2.flow.item1')" class="font-normal"></p>
                      <CardTilt @click="openModal('userFlow')" class="cursor-pointer">
                        <img 
                        src="https://i.imgur.com/j0ui6vo.png"
                        class="object-contain w-full rounded-xl"
                        >
                      </CardTilt>
                    </div>
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
                    { title: $t('project2.principle.item1'), content: $t('project2.principle.item1-1') },
                    { title: $t('project2.principle.item2'), content: $t('project2.principle.item2-1') },
                    { title: $t('project2.principle.item3'), content: $t('project2.principle.item3-1') },
                    { title: $t('project2.principle.item4'), content: $t('project2.principle.item4-1') },
                    { title: $t('project2.principle.item5'), content: $t('project2.principle.item5-1') }
                  ]"
                />
            </template>
          </Section3>
          <!-- Banner -->
          <Parallax 
            class="md:h-[500px] h-64"
            backgroundImage="https://i.imgur.com/sVna7EJ.png"
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
                  <a 
                  target="_blank"
                  href="https://main--6758f1bddc4388960f8ac32f.chromatic.com/">
                    <img 
                      src="https://i.imgur.com/6pMAdyR.png"
                      alt="Banner"
                      class="object-cover mb-8 w-full rounded-2xl xl:rounded-3xl aspect-video"
                    >
                  </a>
                </CardTilt>
                <p 
                v-html="$t('project1.system.item1')"
                class="text-justify"
                >
                </p>
                <br>
                <ListNum :items="[
                  {title: $t('project1.system.item2'), description:  $t('project1.system.item2-1')},
                  {title: $t('project1.system.item3'), description:  $t('project1.system.item3-1')},
                  {title: $t('project1.system.item4'), description:  $t('project1.system.item4-1')},
                  {title: $t('project1.system.item5'), description:  $t('project1.system.item5-1')}
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
                  :buttons="['project2.mockup.tab.item1', 'project2.mockup.tab.item2', 'project2.mockup.tab.item3', 'project2.mockup.tab.item4', 'project2.mockup.tab.item5', 'project2.mockup.tab.item6', 'project2.mockup.tab.item7', 'project2.mockup.tab.item8']">
                    <!-- Tab Contents -->
                    <template #default="{ activeTab }">
                      <div v-if="activeTab === 1" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/jufRYLW.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[5%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item1')"
                            :text="$t('project2.mockup.info.item1-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[30%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project2.mockup.info.item2')"
                            :text="$t('project2.mockup.info.item2-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/DsBvCLK.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item3')"
                            :text="$t('project2.mockup.info.item3-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 2" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/W2lgS9T.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item4')"
                            :text="$t('project2.mockup.info.item4-1')"
                            />
                          </div>
                        </div>
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/gAQInla.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item5')"
                            :text="$t('project2.mockup.info.item5-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[40%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project2.mockup.info.item6')"
                            :text="$t('project2.mockup.info.item6-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/9S548d8.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item7')"
                            :text="$t('project2.mockup.info.item7-1')"
                            />
                          </div>
                          <div class="hidden absolute bottom-[40%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item8')"
                            :text="$t('project2.mockup.info.item8-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 3" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/GnCGBHR.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item9')"
                            :text="$t('project2.mockup.info.item9-1')"
                            />
                          </div>
                        </div>
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/AFk7Mzf.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item10')"
                            :text="$t('project2.mockup.info.item10-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/WSJp0di.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item11')"
                            :text="$t('project2.mockup.info.item11-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 4" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/eY4DThk.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item12')"
                            :text="$t('project2.mockup.info.item12-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/V75oPw1.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item13')"
                            :text="$t('project2.mockup.info.item13-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 5" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/THCpmwq.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item14')"
                            :text="$t('project2.mockup.info.item14-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/1FCGYKF.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item15')"
                            :text="$t('project2.mockup.info.item15-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 6" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/iEmDcUI.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item16')"
                            :text="$t('project2.mockup.info.item16-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/YymbSnK.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item17')"
                            :text="$t('project2.mockup.info.item17-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 7" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/BUfleYe.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item18')"
                            :text="$t('project2.mockup.info.item18-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[40%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project2.mockup.info.item19')"
                            :text="$t('project2.mockup.info.item19-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/RFMQLVo.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item20')"
                            :text="$t('project2.mockup.info.item20-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 8" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/KZdNTSd.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project2.mockup.info.item21')"
                            :text="$t('project2.mockup.info.item21-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[50%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project2.mockup.info.item22')"
                            :text="$t('project2.mockup.info.item22-1')"
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
                        videoSrc="https://i.imgur.com/7H3xCDK.mp4"
                        class="top-1 sm:top-2 w-[77%] sm:w-[64%] xl:w-[77%] object-contain"
                        videoClass="aspect-[8/5] bg-black rounded"
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
              <ImageCompare
                beforeImage="https://i.imgur.com/R7fw8xo.png"
                afterImage="https://i.imgur.com/OAbtsnS.png"
                heightClass="md:h-80 h-72"
                class="mb-8"
                beforeText="EN"
                afterText="ZH"
              />
            <p v-html="$t('project2.handoff.item1')" class="font-normal"></p>
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
                    src="https://i.imgur.com/xZ10FFb.png"
                    class="object-cover mb-8 w-full rounded-2xl xl:rounded-3xl aspect-video"
                  >
                </CardTilt>
                <List 
                customClass="px-6 py-5 bg-B3 rounded-2xl xl:rounded-3xl dark:bg-transparent dark:border dark:border-white"
                :items="[
                    { title: $t('project2.feedback.item1'), content: $t('project2.feedback.item1-1') },
                    { title: $t('project2.feedback.item2'), content: $t('project2.feedback.item2-1') },
                    { title: $t('project2.feedback.item3'), content: $t('project2.feedback.item3-1') },
                    { title: $t('project2.feedback.item4'), content: $t('project2.feedback.item4-1') },
                    { title: $t('project2.feedback.item5'), content: $t('project2.feedback.item5-1') }
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
      <div v-if="currentModal === 'sitemap'" class="w-full  rounded-3xl max-h-[500px] object-cover object-center overflow-y-scroll overflow-hidden">
        <img
          class="object-cover object-center w-full"
          src="https://i.imgur.com/BMLBzRf.png"
          alt="Modal Image"
        />
      </div>
      <div v-if="currentModal === 'userFlow'" class="w-full  rounded-3xl max-h-[500px] object-cover object-center overflow-y-scroll overflow-hidden">
        <img
          class="object-cover object-center w-full"
          src="https://i.imgur.com/j0ui6vo.png"
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
    const currentModal = ref('');

    const openModal = (modalType) => {
      currentModal.value = modalType;
      isModalOpen.value = true;
    };

    return { isModalOpen, openModal, currentModal };
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
  