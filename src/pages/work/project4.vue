<template> 
     <div class="relative pb-6 text-sm sm:pb-10 bg-B4 dark:bg-stone-900 text-stone-800 xs:text-base dark:text-white">
      <Navbar />
      <ProgressBar />
      <BackToTop class="z-20" />
      <!-- Banner -->
      <Banner 
        bannerSrc="https://i.imgur.com/xcDKo8B.jpeg"
      />
      <!-- Content -->
      <div class="absolute left-0 sm:top-[480px] top-[400px] w-full leading-relaxed">
        <!-- Info -->
        <Info 
        :title="$t('project4.core.title')"
        :info1="'2024.11 - 2025.01'"
        :info2="[$t('project4.team.item1'), $t('project4.team.item2')]" 
        :info3="$t('project4.info.item3')"
        :info4="$t('project4.info.item1')"
        :tag="[$t('projectTag.item1'), $t('projectTag.item2'), $t('projectTag.item3'), $t('projectTag.item5'), $t('projectTag.item7')]" 
        :iconsVisible="[true, true, true, true, true, false, false, false, false, true]"
        :linkTo="'https://cafe2-ecru.vercel.app/'"
        :linkType="'a'"
        :icon="icon" 
        :showBTN="true"
        />
        <!-- Main Content -->
        <div>
          <ScrollSpy :sections="sections" />
          <!-- 專案資訊 -->
          <Section1
          id="section1"
          :info1="$t('project4.info.item1')"
          :info2="[$t('project4.demand.item1'), $t('project4.demand.item2'), $t('project4.demand.item3'), $t('project4.demand.item4'), $t('project4.demand.item5'), $t('project4.demand.item6'), $t('project4.demand.item7')]"
          :info4="[
            { avatarSrc: 'https://i.imgur.com/93zadWo.png', job: $t('project4.team.item1'), name: 'Tina Chen' },
            { avatarSrc: 'https://i.imgur.com/93zadWo.png', job: $t('project4.team.item2'), name: 'Tina Chen' }
          ]"
          :content="$t('project4.brief.item1')"
          bannerSrc="https://i.imgur.com/6ViXoml.png"
          >
            <ul class="leading-loose list-disc list-inside">
              <li>
                <span class="font-semibold">
                  {{ $t('project4.brief.item2') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project4.brief.item2-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project4.brief.item3') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project4.brief.item3-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project4.brief.item4') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project4.brief.item4-1') }}
                </span>
              </li>
              <li>
                <span class="font-semibold">
                  {{ $t('project4.brief.item5') }}
                </span>
                <span class="block ml-5 font-normal">
                  {{ $t('project4.brief.item5-1') }}
                </span>
              </li>
            </ul>
          </Section1>
          <!-- 專案概覽 -->
          <Section2
            id="section2"
            :briefs="[
            { title: $t('work.title.item2-1'), content: $t('project4.briefCard.item1') },
            { title: $t('work.title.item2-2'), content: $t('project4.briefCard.item2') },
            { title: $t('work.title.item2-3'), content: $t('project4.briefCard.item3') },
            { title: $t('work.title.item2-4'), content: $t('project4.briefCard.item4') }
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
                  {{ $t('project4.background.item1') }}
                </p>
                <!-- <CardTilt>
                  <img 
                  src="https://images.unsplash.com/photo-1723904186120-aa63a2f7e63e?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                  class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
                >
                </CardTilt> -->
                <Parallax
                backgroundImage="https://images.unsplash.com/photo-1554118811-1e0d58224f24?q=80&w=2894&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
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
                        { title: $t('project4.goal.item1') },
                        { title: $t('project4.goal.item2') },
                        { title: $t('project4.goal.item3') },
                        { title: $t('project4.goal.item4') }
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
                        { title: $t('project4.problem.item1') },
                        { title: $t('project4.problem.item2') }
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
            :title="$t('work.title.item15')"
          >
            <template #content-1>
              <CardTilt>
                <Persona 
                  avatarSrc="https://images.unsplash.com/photo-1543269865-f576bdee5d1d?q=80&w=2940&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
                  :items="{
                    u1: [$t('project4.persona.info.item1'), $t('project4.persona.info.item2'), $t('project4.persona.info.item3')],
                    u2: [$t('project4.persona.difficult.item1')],
                    u3: [$t('project4.persona.insight.item1'), $t('project4.persona.insight.item2')],
                  }"
                  />
              </CardTilt>
            </template>
          </Section3>
          <!-- 圖片 -->
          <EnlargeImg class="mx-auto" imageUrl="https://images.unsplash.com/photo-1453614512568-c4024d13c247?q=80&w=2832&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
          <!-- 執行過程 -->
          <Section3
            id="section7"
            :title="$t('work.title.item16')"
          >
            <template #content-1>
              <TabCard :buttons="['project4.process.item1', 'project4.process.item2']">
                <!-- Background Images -->
                <template #backgrounds>
                  <img src="https://images.unsplash.com/photo-1628258334105-2a0b3d6efee1?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                  <img src="https://images.unsplash.com/photo-1617471346061-5d329ab9c574?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" />
                </template>

                <!-- Tab Contents -->
                <template #default="{ activeTab }">
                  <div v-if="activeTab === 1">
                    <div class="space-y-6 sm:space-y-8">
                      <p v-html="$t('project4.process.item1-1')" class="font-normal"></p>
                      <CardTilt>
                        <img 
                        src="https://i.imgur.com/yxlAvMM.png"
                        class="object-cover w-full rounded-xl aspect-video"
                        >
                      </CardTilt>
                      <div
                      class="flex flex-col gap-2 p-2 text-orange-500 rounded-xl border border-orange-500 transition-colors sm:p-3 group bg-orange-300/20 hover:bg-orange-300/30"
                      >
                        <p class="flex gap-2 items-center font-semibold">
                          <Fa6SolidCircleExclamation />
                          {{ $t('work.title.item8-3') }}
                        </p>
                        <p 
                        v-html="$t('project4.process.item1-2')"
                        class="text-sm">
                        </p>
                      </div>
                    </div>
                  </div>
                  <div v-if="activeTab === 2">
                    <div>
                      <p v-html="$t('project4.process.item2-1')" class="mb-8 font-normal"></p>
                      <CardTilt>
                        <img 
                        src="https://i.imgur.com/E2y3X5X.png"
                        class="object-cover w-full rounded-xl aspect-video"
                        >
                      </CardTilt>
                    </div>
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
                    <CardTilt @click="openModal('sitemap')" class="cursor-pointer">
                      <img 
                        src="https://i.imgur.com/FwKEq3D.png"
                        alt="SiteMap"
                        class="object-cover w-full rounded-xl"
                      >
                    </CardTilt>
                  </div>
                  <!-- User Flow -->
                  <div v-if="activeTab === 2">
                    <div class="space-y-6 sm:space-y-8">
                      <p v-html="$t('project4.flow.item1')" class="font-normal"></p>
                      <CardTilt @click="openModal('userFlow')" class="cursor-pointer">
                        <img 
                        src="https://i.imgur.com/qmfns4K.png"
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
                    { title: $t('project4.principle.item1'), content: $t('project4.principle.item1-1') },
                    { title: $t('project4.principle.item2'), content: $t('project4.principle.item2-1') },
                    { title: $t('project4.principle.item3'), content: $t('project4.principle.item3-1') },
                    { title: $t('project4.principle.item4'), content: $t('project4.principle.item4-1') }
                  ]"
                />
            </template>
          </Section3>
          <!-- Banner -->
          <Parallax 
            class="md:h-[500px] h-64"
            backgroundImage="https://i.imgur.com/wgj2oQY.png"
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
                      src="https://i.imgur.com/11XFA6v.png"
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
                  :buttons="['project4.mockup.tab.item1', 'project4.mockup.tab.item2', 'project4.mockup.tab.item3', 'project4.mockup.tab.item4', 'project4.mockup.tab.item5', 'project4.mockup.tab.item6', 'project4.mockup.tab.item7', 'project4.mockup.tab.item8']">
                    <!-- Tab Contents -->
                    <template #default="{ activeTab }">
                      <div v-if="activeTab === 1" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/HDsblsg.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item1')"
                            :text="$t('project4.mockup.info.item1-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/zRkk4Lh.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item2')"
                            :text="$t('project4.mockup.info.item2-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 2" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/7h45Lmq.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item3')"
                            :text="$t('project4.mockup.info.item3-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/jpT9idj.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item4')"
                            :text="$t('project4.mockup.info.item4-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 3" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/sih7OBx.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item5')"
                            :text="$t('project4.mockup.info.item5-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/viArLD5.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item6')"
                            :text="$t('project4.mockup.info.item6-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 4" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/uRRJTEQ.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item8')"
                            :text="$t('project4.mockup.info.item8-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[12%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project4.mockup.info.item7')"
                            :text="$t('project4.mockup.info.item7-1')"
                            />
                          </div>
                        </div>
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/BYyfiGG.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[40%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item9')"
                            :text="$t('project4.mockup.info.item9-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/5gStBtR.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item10')"
                            :text="$t('project4.mockup.info.item10-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 5" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/myYfwoQ.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item11')"
                            :text="$t('project4.mockup.info.item11-1')"
                            />
                          </div>
                        </div>
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/1HblQik.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item13')"
                            :text="$t('project4.mockup.info.item13-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[20%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project4.mockup.info.item12')"
                            :text="$t('project4.mockup.info.item12-1')"
                            />
                          </div>
                        </div>
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/PKOLIKb.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[30%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item14')"
                            :text="$t('project4.mockup.info.item14-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 6" class="xl:px-12 lg:px-48">
                        <div class="relative mb-8">
                          <img 
                          src="https://i.imgur.com/cVRGPXk.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item16')"
                            :text="$t('project4.mockup.info.item16-1')"
                            />
                          </div>
                          <div class="hidden absolute -left-56 top-[20%] lg:block">
                            <HoverIconButton 
                            customClass="right-0 origin-bottom-right rounded-br"
                            icon="💡"
                            :title="$t('project4.mockup.info.item15')"
                            :text="$t('project4.mockup.info.item15-1')"
                            />
                          </div>
                        </div>
                        <div class="relative mb-">
                          <img 
                          src="https://i.imgur.com/BRdfuW6.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item17')"
                            :text="$t('project4.mockup.info.item17-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 7" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/WDuEud0.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[10%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item18')"
                            :text="$t('project4.mockup.info.item18-1')"
                            />
                          </div>
                        </div>
                      </div>
                      <div v-if="activeTab === 8" class="xl:px-12 lg:px-48">
                        <div class="relative">
                          <img 
                          src="https://i.imgur.com/HUy6fXN.png"
                          class="object-cover mx-auto w-full rounded-2xl xs:w-5/6 lg:w-full xl:rounded-3xl"
                          >
                          <div class="hidden absolute top-[20%] -right-56 lg:block">
                            <HoverIconButton 
                            class=""
                            icon="💡"
                            :title="$t('project4.mockup.info.item19')"
                            :text="$t('project4.mockup.info.item19-1')"
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
                        videoSrc="https://www.youtube.com/embed/uoZ-FD4nUk4?autoplay=1&mute=1&loop=1"
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
                beforeImage="https://i.imgur.com/lKonYyM.png"
                afterImage="https://i.imgur.com/vWX2Gzc.png"
                heightClass="md:h-96 h-64"
                class="mb-8"
                beforeText="Dark"
                afterText="Light"
              />
            <p v-html="$t('project4.handoff.item1')" class="font-normal"></p>
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
                    src="https://i.imgur.com/xcDKo8B.jpeg"
                    class="object-cover mb-8 w-full rounded-2xl xl:rounded-3xl aspect-video"
                  >
                </CardTilt>
                <List 
                customClass="px-6 py-5 bg-B3 rounded-2xl xl:rounded-3xl dark:bg-transparent dark:border dark:border-white"
                :items="[
                    { title: $t('project4.feedback.item1'), content: $t('project4.feedback.item1-1') },
                    { title: $t('project4.feedback.item2'), content: $t('project4.feedback.item2-1') },
                    { title: $t('project4.feedback.item3'), content: $t('project4.feedback.item3-1') },
                    { title: $t('project4.feedback.item4'), content: $t('project4.feedback.item4-1') },
                    { title: $t('project4.feedback.item5'), content: $t('project4.feedback.item5-1') }
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
      <div v-if="currentModal === 'sitemap'" class="w-full lg:aspect-video rounded-3xl max-h-[500px] object-cover object-center overflow-y-scroll overflow-hidden">
        <img
          class="object-cover object-center w-full"
          src="https://i.imgur.com/FwKEq3D.png"
          alt="Modal Image"
        />
      </div>
      <div v-if="currentModal === 'userFlow'" class="w-full  rounded-3xl max-h-[500px] object-cover object-center overflow-y-scroll overflow-hidden">
        <img
          class="object-cover object-center w-full"
          src="https://i.imgur.com/qmfns4K.png"
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
        { id: 'section5', name: 'work.title.item5' },
        { id: 'section6', name: 'work.title.item15' },
        { id: 'section7', name: 'work.title.item16' },
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
  