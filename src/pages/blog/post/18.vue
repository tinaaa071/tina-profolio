<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*VUK2az0HJHzilzN0Rpgv0A.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item3'),
          date: '2024．09．17',
          title: '身為 UI/UX 設計師開發的第一個 Figma Plugin - Shape Mask',
          desc: '設計師為自己打造，Shape Mask 解決遮罩設計的每個細節困擾！',
          brief: '身為一名設計師，我經常思考一個問題：我們是否能用更好的方法解決日常設計中的繁瑣工作？<br>這個念頭促使我從工具的使用者，轉變為工具的創造者，並開發出屬於自己的 Figma Plugin - Shape Mask。',
          menu: [
            { menu: '開發的契機' },
            { menu: '主要功能' },
            { menu: '開發過程' },
            { menu: '實際應用' },
            { menu: '開發心得' },
            { menu: '額外分享：上架後的驚喜' },
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        @navigate="scrollToSection" 
        />
        <Content>
          <div class="flex flex-col gap-4" id="section1">
            <H1 
            :title="'開發的契機'"
            />
            <p>
              作為一名設計師，我經常需要快速建立視覺吸引力強的設計構圖。然而，在 Figma 中處理形狀遮罩（Shape Mask）時，現有功能要達到理想效果往往需要繁瑣的操作步驟。因此，我決定著手開發一款 Plugin，讓設計師能更直覺且高效地完成這類任務。
            </p>
            <div class="grid grid-cols-1 gap-3 sm:grid-cols-2">
              <Callout class="text-sm">
                <p class="mb-2">
                  🎯&nbsp;&nbsp;目標
                </p>
                <ul class="grid gap-2 list-decimal list-inside">
                  <li>減少重複性操作</li>
                  <li>提供多種形狀遮罩物件</li>
                  <li>幫助設計師專注於設計本身</li>
                </ul>
              </Callout>
              <Callout class="text-sm">
                <ul class="grid gap-2 list-none list-inside">
                  <li>
                    🕗&nbsp;&nbsp;開發時間：兩週
                  </li>
                  <li>
                    🕗&nbsp;&nbsp;上架日期：2024．11．06
                  </li>
                </ul>
              </Callout>
            </div>
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1200/1*M4zkxVmUiNAI9Ls97HYZuA.png"
            />
            <Mention 
              showNote="true"
              note="📌&nbsp;&nbsp;使用 Shape Mask："
              :isExternal="true"
              :link="'https://www.figma.com/community/plugin/1420953914431407843/shape-mask'" 
              :title="'Shape Mask'" 
              :content="'This plugin allows you to add unique mask effects and custom shape cropping to images.'" 
              :image="'https://www.figma.com/community/icon?resource_id=1420953914431407843&resource_type=plugin'" 
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'主要功能'"
            />
            <p>
              Shape Mask 的功能設計以簡單高效為核心，以下是主要特色：
            </p>
            <ListNum 
            :items="list1"
            customClass="space-y-4"
            >
              <template #slot-1>
                <div class="grid grid-cols-2 gap-2 mt-4">
                  <CreditImg 
                    imgSrc="https://cdn-images-1.medium.com/max/1200/1*VuXsdRDiJ7OednjghC5L3g.png"
                    imgCredit="預設遮罩效果"
                    aspectRatio="aspect-square"
                  />
                  <CreditImg 
                    imgSrc="https://cdn-images-1.medium.com/max/1200/1*w0qyHLmJawCxxVMUPX5Mug.png"
                    imgCredit="反轉遮罩效果"
                    aspectRatio="aspect-square"
                  />
                </div>
              </template>
              <template #slot-3>
                <CreditImg 
                  imgSrc="https://cdn-images-1.medium.com/max/1600/1*-yvhugQmAydr9NDv-VJytg.png"
                  imgCredit="自行上傳 svg 檔案套用"
                  class="mt-4"
                />
              </template>
            </ListNum>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'開發過程'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*3T0Z4_ye69FPswar550qww.png"
              imgCredit="Credit: Unsplash"
            />
            <p>
              開發這款 Plugin 是一次充滿挑戰但又有趣的旅程。以下是過程中遇到的一些難題以及我的解決方式：
            </p>
            <ListDisc :items="list2" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*cEMMsGq-FPVra1eDADHV8Q.png"
              imgCredit="我在 Figma 設計了 Plugin 呈現的 UI"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'實際應用'"
            customClass="space-y-4"
            />
            <ListDisc :items="list3" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*pjP_lN4tlMlxfQ_YPLN0rw.png"
              imgCredit="使用 Plugin 製作出的 Banner"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'開發心得'"
            />
            <p>
              這次開發 Shape Mask 的經歷讓我深刻體會到，設計師懂一點程式開發很有幫助。不僅能解決自己的工作痛點，還能幫助其他人提升效率。雖然開發的過程經歷了非常多的挫折、遇到了無數個 bug，但這次經驗也啟發我去探索更多跨界技能的可能性，並激勵我持續挑戰自我。
            </p>
            <Video videoSrc="https://www.youtube.com/embed/_6jO-zrU5Do?autoplay=1&mute=1&loop=1" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section6">
            <H1 
            :title="'📢 額外分享：上架後的驚喜'"
            />
            <p>
              上架 Shape Mask 幾天後，我收到來自 Adobe Express 團隊的聯絡，表示對這款 Plugin 的功能很感興趣，並希望能將它上架到 Adobe 平台中，讓更多設計師受益。
            </p>
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*tz3SqnucYu1ZbSZr0Z4znA.png"
              imgCredit="來自 Adobe 的信件"
            />
            <p>
              這是我未曾預料的發展，也讓我更加相信跨平台合作的潛力。這次機會不僅讓我學到如何適配 Adobe 的環境與需求，也激勵我去思考更多元化的發展方向，例如：
            </p>
            <ListDisc :items="list4" />
            <p>
              這一合作的可能性為 Shape Mask 開啟了全新的篇章，或許我們也能期待未來在 Adobe Express 看到這款 Plugin。
            </p>
          </div>
        </Content>
        </div>
      </template>
    </Layout>
  </div>
  <!-- More Like -->
  <More 
  :showMore="true"
  :posts="posts" 
  />
  <Footer />
</template>

<script>
export default {
  data() {
    return {
      list1: [
        {
          title: "快速套用形狀遮罩",
          description: "使用者可以一鍵套用遮罩，支援多種形狀選項（圓形、三角形、自定義形狀等）。",
        },
        {
          title: "反轉遮罩效果",
          description: "除了基本的遮罩功能，Shape Mask 還支持反轉遮罩效果，擴展了設計的靈活性。",
        },
        {
          title: "提供簡單直觀的操作界面",
          description: "以各種形狀風格做為分類篩選，用戶可以快速找到適合的形狀並套用，點擊切換按鈕馬上反轉遮罩效果。",
        },
        {
          title: "自定義遮罩形狀",
          description: "用戶可以上傳自定義形狀作為遮罩，你可以親自設計特別的 svg 形狀，並應用於你的設計之中。",
        }
      ],
      list2: [
        {
          title: "技術學習曲線",
          description: "儘管我是設計師，對 JavaScript 和 Figma API 不熟悉。為此，我花時間學習相關知識並研究 Figma 的技術文件。Figma 的文件中提到建議使用 Typescript 來開發，因為我從來沒有使用過此語言，對我來說完全是個陌生領域，為此我也去研究了相關文件資料。",
        },
        {
          title: "資源不足",
          description: "網路上對於開發 Figma Plugin 的資源並不多，尤其鮮少有中文開發者的資源，所以我大部分是尋求外文網站的資源。",
        },
        {
          title: "性能優化",
          description: "插件在處理大量圖層時，初版的執行效率較低，並且屢次失敗達不到我期望的效果，經過幾次測試和調整後，我優化了算法，減少了處理時間。",
        },
        {
          title: "用戶體驗",
          description: "如何設計 Plugin 的界面，讓功能不僅強大而且易用，是一個重要課題。尤其身為一名 UI/UX 設計師，介面的呈現更是我需要花心思的部分。我決定以簡單直觀的介面來呈現，強調功能的效果，讓使用者較容易上手。",
        }
      ],
      list3: [
        {
          description: "在 UI 設計中，輕鬆處理用於裝飾的創意遮罩設計。",
        },
        {
          description: "減少操作時間，讓團隊能更專注於設計的創意部分。",
        },
        {
          description: "讓單調的設計增添不同的視覺效果。",
        }
      ],
      list4: [
        {
          description: "調整功能以支援多平台用戶。",
        },
        {
          description: "與其他開發者合作，汲取更豐富的回饋與建議。",
        }
      ],
      posts: [
        {
          id: 1,
          link: '/',
          title: "Post 1",
          category: this.$t('blog.item3'),
          image: "https://images.unsplash.com/photo-1628768534904-cf74bc8b897d?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          date: "2024．09．02",
        },
        {
          id: 2,
          link: '/about',
          title: "Post 2",
          category: this.$t('blog.item2'),
          image: "https://images.unsplash.com/photo-1628768534895-ff9185e7edbc?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          date: new Date().toLocaleDateString(),
        },
        {
          id: 2,
          link: '/post/1',
          title: "Post 2",
          category: this.$t('blog.item3'),
          image: "https://images.unsplash.com/photo-1628766416710-61d6f15f32b9?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          date: new Date().toLocaleDateString(),
        },
        {
          id: 2,
          link: '/post/1',
          title: "Post 2",
          category: this.$t('blog.item4'),
          image: "https://images.unsplash.com/photo-1723920515274-ace3503adad6?q=80&w=2826&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
          date: new Date().toLocaleDateString(),
        }
      ],
    };
  },
  computed: {
    filteredPosts() {
      // Optional: Apply any additional filtering here if needed
      return this.posts;
    }
  },
  methods: {
    scrollToSection(targetId) {
      const element = document.getElementById(targetId);
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
};
</script>