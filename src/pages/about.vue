<template>
  <div class="pb-6 text-sm bg-white sm:pb-10 dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Navbar />
    <ProgressBar />
    <BackToTop class="z-20" />
    <!-- Profile 區塊 -->
     <div class="pt-40 pb-8 mx-auto md:pb-16 md:px-10 xl:px-28 md:pt-44">
      <div class="w-10/12 mx-auto bg-white cursor-default dark:bg-stone-900 dark:text-white text-stone-800">
            <div class="flex flex-col items-center w-full gap-6 md:gap-10 md:flex-row">
              <!-- Img -->
              <div class="relative w-3/4 xs:w-1/2 md:w-1/3 lg:w-1/4">
                <div class="absolute z-10 -left-4 -top-12 w-52">
                  <ChatBubble />
                </div>
                <CardTilt class="flex items-center w-full h-full shadow-xs aspect-square"  >
                  <img src="https://i.imgur.com/aBGSFku.jpeg" alt="" class="object-cover object-center overflow-hidden w-full h-full rounded-[64px]">
                </CardTilt>
              </div>
              <!-- Content -->
               <div class="w-full md:w-2/3">
                <p class="mb-4 text-xl font-semibold md:mb-6 md:text-2xl">
                  {{ $t('about.info.item2') }}
                </p>
                <p v-html="$t('about.info.item3')" class="font-normal text-justify">
                </p>
               </div>
            </div>
            
      </div>
     </div>
    <!-- Value 區塊 -->
    <aboutSection 
    :title="$t('about.value.T1')"
    class="bg-B4 dark:border-y dark:border-white/20"
    >
      <div class="flex flex-col">
      <!-- List Items -->
      <div class="flex flex-col overflow-hidden divide-y rounded-2xl sm:rounded-3xl dark:border dark:border-white">
        <!-- List Items -->
        <div
          v-for="(item, index) in [
            { title: 'about.value.V1', content: 'about.value.V1-1' },
            { title: 'about.value.V2', content: 'about.value.V2-1' },
            { title: 'about.value.V3', content: 'about.value.V3-1' }
          ]"
          :key="index"
          class="flex gap-6 p-6 font-semibold transition-colors duration-100 ease-in-out md:p-8 hover:bg-white dark:hover:bg-stone-800"
        >
          <span>
            {{ index + 1 }}.
          </span>
          <div>
            <!-- Title -->
            <p class="mb-2">
              {{ $t(item.title) }}
            </p>
            <!-- Content -->
            <p class="font-medium text-stone-700 dark:text-stone-300">
              {{ $t(item.content) }}
            </p>
          </div>
        </div>
      </div>
    </div>
    </aboutSection>
    <!-- Skills 區塊 -->
    <aboutSection
    :title="$t('about.skill.T1')"
    >
      <div class="flex flex-wrap gap-2 sm:gap-3">
        <Tag
        :tag="[$t('about.skill.S1'), $t('about.skill.S2'), $t('about.skill.S3'), $t('about.skill.S4'), $t('about.skill.S5'), $t('about.skill.S6'), $t('about.skill.S7'), $t('about.skill.S8'), $t('about.skill.S9'), $t('about.skill.S10'), $t('about.skill.S11')]" 
        class="bg-B4"
        />
      </div>
    </aboutSection>
    <!-- Language 區塊 -->
    <aboutSection
    :title="$t('about.language.T1')"
    >
    <div class="grid grid-cols-1 gap-4 xs:gap-6 xs:grid-cols-2">
        <!-- List Items -->
        <div
          v-for="(item, index) in [
            { title: 'about.language.S1', content: 'about.language.L1' },
            { title: 'about.language.S2', content: 'about.language.L2' }
          ]"
          :key="index"
          class="flex w-full gap-6 px-6 py-5 font-semibold border shadow rounded-2xl sm:rounded-3xl border-B4"
        >
          <div>
            <!-- Title -->
            <p class="mb-2">
              {{ $t(item.title) }}
            </p>
            <!-- Content -->
            <p class="text-sm font-medium text-stone-500 dark:text-stone-300">
              {{ $t(item.content) }}
            </p>
          </div>
        </div>
      </div>
    </aboutSection>
    <!-- Education 區塊 -->
    <aboutSection
    :title="$t('about.education.T1')"
    >
    <div class="grid grid-cols-1 gap-4 xs:gap-6 xs:grid-cols-2">
        <!-- List Items -->
        <div
          class="flex w-full gap-6 px-6 py-5 font-semibold border shadow rounded-2xl sm:rounded-3xl border-B4"
        >
          <div>
            <!-- Title -->
            <p class="mb-2">
              {{ $t('about.education.S1') }}
            </p>
            <!-- Content -->
            <p class="text-sm font-medium text-stone-500 dark:text-stone-300">
              {{ $t('about.education.L1') }}
              <br>
              <span class="text-xs text-stone-400 dark:text-stone-400">
                {{ $t('about.education.L2') }}
              </span>
            </p>
          </div>
        </div>
      </div>
    </aboutSection>
    <!-- Learning 區塊 -->
    <aboutSection
    :title="$t('about.certificate.T1')"
    >
    <div class="grid grid-cols-1 gap-6 xs:grid-cols-2 sm:grid-cols-3 lg:grid-cols-4">
        <!-- List Items -->
        <LearnCard
        v-for="(card, index) in [
        { title: $t('about.certificate.S1'), info: $t('about.certificate.L1'), cardSrc: 'https://tina-chen.netlify.app/Images/CareFit/certification1.jpg' },
        { title: $t('about.certificate.S2'), info: $t('about.certificate.L2'), cardSrc: 'https://images.credly.com/size/680x680/images/86a3283f-3e35-494f-82da-3fb3e89ba223/image.png' },
        { title: $t('about.certificate.S3'), info: $t('about.certificate.L3'), cardSrc: 'https://i.imgur.com/F9scbI7.png' },
        { title: $t('about.certificate.S4'), info: $t('about.certificate.L4'), cardSrc: 'https://i.meee.com.tw/tD70DVW.jpg' },
        { title: $t('about.certificate.S5'), info: $t('about.certificate.L5'), cardSrc: 'https://i.meee.com.tw/6kEoK3D.jpg' },
        { title: $t('about.certificate.S6'), info: $t('about.certificate.L5'), cardSrc: 'https://tina-chen.netlify.app/Images/CareFit/competition.png' },
        // Add more cards as needed
      ]"
      :key="index"
      :title="card.title"
      :info="card.info"
      :cardSrc="card.cardSrc"
    />
      </div>
    </aboutSection>
    <!-- Tools 區塊 -->
    <aboutSection
    :title="$t('about.tool.T1')"
    >
      <div class="grid grid-cols-1 gap-6 cursor-default md:grid-cols-2">
        <!-- 介面設計 -->
        <div class="flex flex-col gap-3 md:gap-4 md:flex-row">
          <p class="text-sm font-semibold text-stone-400 md:max-w-28 text-wrap">
            {{ $t('about.tool.S1') }}
          </p>
          <div class="flex flex-row flex-wrap gap-4 xs:gap-x-6 xs:gap-y-3">
            <Icon
                v-for="(image, index) in [
                  { url: 'https://i.imgur.com/7pnxjJF.png', tooltip: 'Figma' },
                  { url: 'https://i.imgur.com/2YcIFwQ.png', tooltip: 'Sketch' },
                  { url: 'https://logos-world.net/wp-content/uploads/2021/02/Google-Analytics-Logo.png', tooltip: 'GA' }
                ]"
                :key="index"
                :imageUrl="image.url"
                :tooltipText="image.tooltip"
              />
          </div>
        </div>
        <!-- 程式開發 -->
        <div class="flex flex-col gap-3 md:gap-4 md:flex-row">
          <p class="text-sm font-semibold text-stone-400 md:max-w-28 text-wrap">
            {{ $t('about.tool.S2') }}
          </p>
          <div class="flex flex-row flex-wrap gap-4 xs:gap-x-6 xs:gap-y-3">
            <Icon
                v-for="(image, index) in [
                  { url: 'https://i.imgur.com/zIeXvD3.png', tooltip: 'Vue' },
                  { url: 'https://i.imgur.com/28m1SmQ.png', tooltip: 'Vite' },
                  { url: 'https://i.imgur.com/szgrbI5.png', tooltip: 'Git' },
                  { url: 'https://i.imgur.com/HAqgRy7.png', tooltip: 'Tailwind' },
                  { url: 'https://i.imgur.com/FWRKUGC.png', tooltip: 'Bootstrap' },
                  { url: 'https://i.imgur.com/oCdyvHY.png', tooltip: 'Sass' },
                  { url: 'https://i.imgur.com/2vbL70p.png', tooltip: 'Wordpress' },
                  { url: 'https://i.imgur.com/D4xOlui.png', tooltip: 'Webflow' },
                ]"
                :key="index"
                :imageUrl="image.url"
                :tooltipText="image.tooltip"
              />
          </div>
        </div>
        <!-- 設計工具 -->
        <div class="flex flex-col gap-3 md:gap-4 md:flex-row">
          <p class="text-sm font-semibold text-stone-400 md:max-w-28 text-wrap">
            {{ $t('about.tool.S3') }}
          </p>
          <div class="flex flex-row flex-wrap gap-4 xs:gap-x-6 xs:gap-y-3">
            <Icon
                v-for="(image, index) in [
                  { url: 'https://i.imgur.com/anAgplx.png', tooltip: 'PS' },
                  { url: 'https://i.imgur.com/4nfRaVx.png', tooltip: 'AI' },
                  { url: 'https://i.imgur.com/NYeHQWZ.png', tooltip: 'Spline' },
                  { url: 'https://i.imgur.com/s2K4MBG.png', tooltip: 'Blender' },
                  { url: 'https://i.imgur.com/nQ5gGur.png', tooltip: 'Lottie' },
                ]"
                :key="index"
                :imageUrl="image.url"
                :tooltipText="image.tooltip"
              />
          </div>
        </div>
        <!-- 專案管理 -->
        <div class="flex flex-col gap-3 md:gap-4 md:flex-row">
          <p class="text-sm font-semibold text-stone-400 md:max-w-28 text-wrap">
            {{ $t('about.tool.S4') }}
          </p>
          <div class="flex flex-row flex-wrap gap-4 xs:gap-x-6 xs:gap-y-3">
            <Icon
                v-for="(image, index) in [
                  { url: 'https://i.imgur.com/kAMkFzO.png', tooltip: 'Notion' },
                  { url: 'https://i.imgur.com/meFkjAw.png', tooltip: 'ClickUp' },
                  { url: 'https://i.imgur.com/9DsxTqY.png', tooltip: 'Trello' },
                  { url: 'https://i.imgur.com/kpRhY1W.png', tooltip: 'Miro' },
                ]"
                :key="index"
                :imageUrl="image.url"
                :tooltipText="image.tooltip"
              />
          </div>
        </div>
      </div>
    </aboutSection>
    <!-- <div class="py-8 mx-auto md:py-10 bg-B3 dark:bg-stone-800 xl:py-16">
      <p class="px-6 mb-8 text-xl font-semibold sm:px-10 xl:px-28">
        {{ $t('about.tool.T1') }}
      </p>
      <ToolMarquee />
    </div> -->
    <!-- Work 區塊 -->
    <aboutSection
    :title="$t('about.work.T1')"
    class="space-y-4 md:py-8 xs:space-y-6"
    >
      <!-- Work 1 -->
      <WorkAccordion
      v-for="(section, index) in section1"
      :key="index"
      :title="section.title"
      :info="section.info"
      :time="section.time"
      :desc="section.desc"
      :showLogo="section.showLogo"
      :logoSrc="section.logoSrc"
      :sections="section.sections"
      :showAtt="true"
      :items="section.items"
      :showModalBtn="section.showModalBtn"
      :showLinkBtn="section.showLinkBtn"
      />
      <!-- Work 2 -->
      <WorkAccordion
      v-for="(section, index) in section2"
      :key="index"
      :title="section.title"
      :info="section.info"
      :time="section.time"
      :desc="section.desc"
      :showLogo="section.showLogo"
      :logoSrc="section.logoSrc"
      :sections="section.sections"
      :showAtt="false"
      :items="section.items"
      :showModalBtn="section.showModalBtn"
      :showLinkBtn="section.showLinkBtn"
      />
      <!-- Work 3 -->
      <WorkAccordion
      v-for="(section, index) in section3"
      :key="index"
      :title="section.title"
      :info="section.info"
      :time="section.time"
      :desc="section.desc"
      :showLogo="section.showLogo"
      :logoSrc="section.logoSrc"
      :sections="section.sections"
      :showAtt="true"
      :items="section.items"
      :showModalBtn="section.showModalBtn"
      :showLinkBtn="section.showLinkBtn"
      />
      <!-- Work 4 -->
      <WorkAccordion
      v-for="(section, index) in section4"
      :key="index"
      :title="section.title"
      :info="section.info"
      :time="section.time"
      :desc="section.desc"
      :showLogo="section.showLogo"
      :logoSrc="section.logoSrc"
      :sections="section.sections"
      :showAtt="false"
      :items="section.items"
      :showModalBtn="section.showModalBtn"
      :showLinkBtn="section.showLinkBtn"
      />
      <Modal
          v-if="currentModalId !== null"
          :show="currentModalId !== null"
          @close="closeModal"
        >
        
        </Modal>
    </aboutSection>
  </div>
  <!-- Footer -->
  <Footer />
</template>

<script>
import { ref, computed } from 'vue';

export default {
  data() {
    return {
      currentModalId: ref(null), // 控制 Modal 開關
    };
  },
  methods: {
    openModal(modalId) {
      this.currentModalId = modalId;
    },
    closeModal() {
      this.currentModalId = null;
    },
  },
  computed: {
    section1() {
      return [
        {
          title: this.$t('about.work.exp1.title'),
          info: this.$t('about.work.exp1.info'),
          time: '2023.04 - Now',
          desc: this.$t('about.work.exp1.desc'),
          showLogo: true,
          logoSrc: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSD8zXG2okHKCKRAsdO5TDkYTHX-MP_Gn4Wdw&s',
          sections: [
            {
              listTitle: this.$t('about.work.exp1.L1.title'),
              listItems: [
                this.$t('about.work.exp1.L1.1'),
                this.$t('about.work.exp1.L1.2'),
                this.$t('about.work.exp1.L1.3'),
                this.$t('about.work.exp1.L1.4'),
                this.$t('about.work.exp1.L1.5'),
                this.$t('about.work.exp1.L1.6'),
                this.$t('about.work.exp1.L1.7'),
                this.$t('about.work.exp1.L1.8'),
              ],
            },
            {
              listTitle: this.$t('about.work.exp1.L2.title'),
              listItems: [
                this.$t('about.work.exp1.L2.1'),
                this.$t('about.work.exp1.L2.2'),
                this.$t('about.work.exp1.L2.3'),
                this.$t('about.work.exp1.L2.4'),
                this.$t('about.work.exp1.L2.5'),
                this.$t('about.work.exp1.L2.6'),
                this.$t('about.work.exp1.L2.7'),
                this.$t('about.work.exp1.L2.8'),
              ],
            },
          ],
          items: [
            {
              id: 1,
              imgSrc: 'https://cdn-images-1.medium.com/max/1600/1*VUK2az0HJHzilzN0Rpgv0A.png',
              linkTo: 'https://www.figma.com/community/plugin/1420953914431407843/shape-mask',
              showModalBtn: false,
              showLinkBtn: true,
            },
            {
              id: 2,
              imgSrc: 'https://i.imgur.com/TMgRmfr.png',
              linkTo: 'https://medium.com/@tina.uiux',
              showModalBtn: false,
              showLinkBtn: true,
            },
          ],
          showModalBtn: false,
          showLinkBtn: true,
        },
        // 可加入更多資料
      ];
    },
    section2() {
      return [
        {
          title: this.$t('about.work.exp2.title'),
          info: this.$t('about.work.exp2.info'),
          time: '2022.10 - 2023.03',
          desc: this.$t('about.work.exp2.desc'),
          showLogo: true,
          logoSrc: 'https://media.cakeresume.com/image/upload/s--8XCkXfyg--/c_pad,fl_png8,h_400,w_400/v1711896073/r6akdaguveqg0uhxbl1h.png',
          sections: [
            {
              listTitle: this.$t('about.work.exp2.L1.title'),
              listItems: [
                this.$t('about.work.exp2.L1.1'),
                this.$t('about.work.exp2.L1.2'),
                this.$t('about.work.exp2.L1.3'),
                this.$t('about.work.exp2.L1.4'),
                this.$t('about.work.exp2.L1.5'),
                this.$t('about.work.exp2.L1.6'),
                this.$t('about.work.exp2.L1.7'),
                this.$t('about.work.exp2.L1.8'),
              ],
            },
            {
              listTitle: this.$t('about.work.exp2.L2.title'),
              listItems: [
                this.$t('about.work.exp2.L2.1'),
                this.$t('about.work.exp2.L2.2'),
              ],
            },
          ],
          items: [
            {
              id: 1,
              imgSrc: 'https://i.imgur.com/TMgRmfr.png',
              linkTo: 'https://medium.com/@tina.uiux',
              showModalBtn: false,
              showLinkBtn: true,
            },
            {
              id: 2,
              imgSrc: 'https://cdn-images-1.medium.com/max/1600/1*VUK2az0HJHzilzN0Rpgv0A.png',
              linkTo: 'https://www.figma.com/community/plugin/1420953914431407843/shape-mask',
              showModalBtn: false,
              showLinkBtn: true,
            },
          ],
          showModalBtn: false,
          showLinkBtn: true,
        },
        // 可加入更多資料
      ];
    },
    section3() {
      return [
        {
          title: this.$t('about.work.exp3.title'),
          info: this.$t('about.work.exp3.info'),
          time: '2021.06 - 2022.02',
          desc: this.$t('about.work.exp3.desc'),
          showLogo: true,
          logoSrc: 'https://tina-chen.netlify.app/Images/CareFit/company1.jpeg',
          sections: [
            {
              listTitle: this.$t('about.work.exp3.L1.title'),
              listItems: [
                this.$t('about.work.exp3.L1.1'),
                this.$t('about.work.exp3.L1.2'),
                this.$t('about.work.exp3.L1.3'),
                this.$t('about.work.exp3.L1.4'),
                this.$t('about.work.exp3.L1.5'),
                this.$t('about.work.exp3.L1.6'),
                this.$t('about.work.exp3.L1.7'),
                this.$t('about.work.exp3.L1.8'),
              ],
            },
            {
              listTitle: this.$t('about.work.exp3.L2.title'),
              listItems: [
                this.$t('about.work.exp3.L2.1'),
                this.$t('about.work.exp3.L2.2'),
                this.$t('about.work.exp3.L2.3'),
                this.$t('about.work.exp3.L2.4'),
                this.$t('about.work.exp3.L2.5'),
                this.$t('about.work.exp3.L2.6'),
              ],
            },
          ],
          items: [
            {
              id: 1,
              imgSrc: 'https://tina-chen.netlify.app/Images/CareFit/attachment1.png',
              showModalBtn: false,
              showLinkBtn: false,
            },
            {
              id: 2,
              imgSrc: 'https://tina-chen.netlify.app/Images/CareFit/attachment2.png',
              showModalBtn: false,
              showLinkBtn: false,
            },
          ],
          showModalBtn: false,
          showLinkBtn: true,
        },
        // 可加入更多資料
      ];
    },
    section4() {
      return [
        {
          title: this.$t('about.work.exp4.title'),
          info: this.$t('about.work.exp4.info'),
          time: '2021.02 - 2021.06',
          desc: this.$t('about.work.exp4.desc'),
          showLogo: true,
          logoSrc: 'https://tina-chen.netlify.app/Images/CareFit/company2.jpeg',
          sections: [
            {
              listTitle: this.$t('about.work.exp4.L1.title'),
              listItems: [
                this.$t('about.work.exp4.L1.1'),
                this.$t('about.work.exp4.L1.2'),
                this.$t('about.work.exp4.L1.3'),
                this.$t('about.work.exp4.L1.4'),
                this.$t('about.work.exp4.L1.5'),
                this.$t('about.work.exp4.L1.6'),
                this.$t('about.work.exp4.L1.7')
              ],
            },
            {
              listTitle: this.$t('about.work.exp4.L2.title'),
              listItems: [
                this.$t('about.work.exp4.L2.1'),
                this.$t('about.work.exp4.L2.2'),
                this.$t('about.work.exp4.L2.3'),
                this.$t('about.work.exp4.L2.4'),
                this.$t('about.work.exp4.L2.5'),
                this.$t('about.work.exp4.L2.6'),
              ],
            },
          ],
          items: [
            {
              id: 1,
              imgSrc: 'https://tina-chen.netlify.app/Images/CareFit/attachment1.png',
              showModalBtn: false,
              showLinkBtn: false,
            },
            {
              id: 2,
              imgSrc: 'https://tina-chen.netlify.app/Images/CareFit/attachment2.png',
              showModalBtn: false,
              showLinkBtn: false,
            },
          ],
          showModalBtn: false,
          showLinkBtn: true,
        },
        // 可加入更多資料
      ];
    },
    
  },
};
</script>
