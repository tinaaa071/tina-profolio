<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*hx609LG91bVhVTfCBCf_bA.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item4'),
          date: '2024．09．24',
          title: '5 個 UI 配色網站資源：提升設計質感的必備工具',
          desc: '快速提升設計質感！必收藏的 5 個 UI 配色資源',
          brief: '在設計網頁或移動應用程式的過程中，選擇合適的顏色組合不僅能增強視覺效果，還能提升用戶體驗。'
        }"
        :showCredit="true"
        :showMenu="true"
        @navigate="scrollToSection" 
        />
        <Content>
          <div class="flex flex-col gap-4" id="section1">
            <H1 
            :title="'Coolors'"
            :link="'https://coolors.co/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*3WX7hEziYG-zY2jy"
              imgCredit="Credit: Coolors"
            />
            <p>
              Coolors 是一個廣受設計師喜愛的配色工具，它提供了一個簡單的界面，能夠快速生成色彩方案。你可以通過點擊按鈕生成隨機顏色，或者手動選擇顏色並鎖定它們，然後讓系統根據選擇的顏色創建一個和諧的配色方案。此外，Coolors 還支持導出色彩方案、查看色彩值、並提供多種色盲友好的配色選擇，適合任何設計需求。
            </p>
            <div>
              <span>優點：</span>
              <ListDisc :items="list1" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'Color Hunt'"
            :link="'https://colorhunt.co/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*KOuqSKDZ136S_rou.png"
              imgCredit="Credit: Color Hunt"
            />
            <p>
              Color Hunt 是一個由設計師社群貢獻的免費配色網站。這裡的配色方案經過精心挑選，並且適合不同風格的設計需求。無論你是做網站、應用程式還是其他類型的視覺設計，都能在這裡找到合適的色彩組合。
            </p>
            <div>
              <span>優點：</span>
              <ListDisc :items="list2" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'Adobe Color'"
            :link="'https://color.adobe.com/zh/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*dfCyhs4kNPAei13s.JPG"
              imgCredit="Credit: Adobe Color"
            />
            <p>
              Adobe Color 是一款強大的配色工具，它不僅提供了基本的色輪配色功能，還可以根據不同的配色原則（如互補色、類似色等）來生成色彩方案。你還可以從圖片中提取顏色，創建與圖像相符的色彩組合，這對於需要精確色彩配合的設計師來說非常有幫助。
            </p>
            <div>
              <span>優點：</span>
              <ListDisc :items="list3" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'Color Palette Ideas'"
            :link="'https://colorpalettes.net/'"
            />
            <div class="grid grid-cols-2 gap-2">
              <CreditImg 
                imgSrc="https://cdn-images-1.medium.com/max/1200/0*7AZ5nymFFCPrvhyh.png"
                imgCredit="Credit: Color Palette Ideas"
              />
              <CreditImg 
                imgSrc="https://cdn-images-1.medium.com/max/1200/0*7szWV3NiGVLUCWR8.png"
                imgCredit="Credit: Color Palette Ideas"
              />
            </div>
            <p>
              創建一個有吸引力的配色方案有時候會讓人感到困惑，特別是當你需要靈感來啟發設計時。這時，Color Palette Ideas 就是你尋找配色方案的最佳助手。這個網站提供了大量由專業設計師和社群分享的顏色組合，你可以根據不同的風格（例如復古、現代、極簡等）進行選擇。
            </p>
            <div>
              <span>優點：</span>
              <ListDisc :items="list4" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'Material UI'"
            :link="'https://materialui.co/colors'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*PIOtjKJjoY2B20wI"
              imgCredit="Credit: Material UI"
            />
            <p>
              Material UI 是一個專為遵循 Google Material Design 規範的應用而設計的 UI 庫。它不僅提供了大量現成的設計組件，還有一個專門的配色工具，可以幫助你選擇符合 Material Design 規範的顏色方案。Material UI 提供的顏色組合經過精心設計，能夠在視覺上保持平衡與對比，並確保各種 UI 元素之間有良好的可讀性和可操作性。
            </p>
            <div>
              <span>優點：</span>
              <ListDisc :items="list5" />
            </div>
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
          description: "快速生成色彩方案",
        },
        {
          description: "色盲友好的選項",
        },
        {
          description: "色彩代碼支持（HEX、RGB 等）。",
        }
      ],
      list2: [
        {
          description: "免費且簡單易用",
        },
        {
          description: "提供設計師社群推薦的顏色組合",
        },
        {
          description: "色彩方案風格多樣",
        }
      ],
      list3: [
        {
          description: "提供多種配色規則",
        },
        {
          description: "圖片色彩提取",
        },
        {
          description: "與 Adobe Creative Cloud 整合",
        }
      ],
      list4: [
        {
          description: "提供多樣的配色風格，適應不同需求",
        },
        {
          description: "社群貢獻的顏色組合，靈感源源不斷",
        },
        {
          description: "可以輕鬆找到符合特定情感和氛圍的顏色",
        }
      ],
      list5: [
        {
          description: "專為 Material Design 設計，確保一致性",
        },
        {
          description: "提供現成的 UI 元素和配色方案",
        },
        {
          description: "配色方案經過精心設計，適用於各種應用界面",
        }
      ],
      list6: [
        {
          title: "支援多語言",
          description: "考慮不同語言和文化背景的用戶。",
        },
        {
          title: "輔助技術支援",
          description: "如屏幕閱讀器的兼容性、清晰的按鈕標籤等。",
        },
        {
          title: "色彩選擇",
          description: "避免僅用顏色傳遞資訊，為色盲用戶提供替代選項。",
        }
      ],
      posts: [
        {
          id: 1,
          link: '/blog/post/2',
          title: "UI/UX 設計師如何培養美感？提升設計視野的實用指南",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*Qjgp1iIbw1IY2ww1AxfbPg.png",
          date: "2024．09．10",
        },
        {
          id: 2,
          link: '/blog/post/7',
          title: "從零開始成為 UI/UX 設計師：自學路徑指南",
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*yJi3pvZRfffeHToNDhtSmQ.png",
          date: "2024．10．20",
        },
        {
          id: 3,
          link: '/blog/post/14',
          title: "Bento Grid UI：靈感來自便當盒的介面設計風格",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*XmqGmjWlFW0ZdY8xyTCGqA.png",
          date: "2024．11．08",
        },
        {
          id: 4,
          link: '/blog/post/15',
          title: "《設計心理學》 - 理解人類行為與設計的橋樑",
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*l9LTo-VAunwN9UZeeoca4Q.png",
          date: "2024．11．12",
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