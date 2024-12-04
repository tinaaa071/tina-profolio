<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*FXqQSo8i5KrmhKGlImNUbA.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item4'),
          date: '2024．09．24',
          title: '12 款必備 Figma Plugins 推薦，提升設計效率的秘密武器',
          desc: '設計更輕鬆！12 款 Figma 插件讓你事半功倍！',
          brief: '作為設計師，我們每天都在與設計工具打交道，而 Figma 的強大與靈活性使其成為眾多設計師的首選。然而，真正讓 Figma 如虎添翼的，正是那些功能強大的插件（Plugins）。',
        }"
        :showCredit="true"
        :showMenu="true"
        />
        <Content>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Unsplash'"
            :link="'https://www.figma.com/community/plugin/738454987945972471/unsplash'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*HezdGD-5nA_pb9gb"
              imgCredit="Credit: Unsplash"
            />
            <ListDisc :items="list1" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Iconify'"
            :link="'https://www.figma.com/community/plugin/735098390272716381/iconify'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*2kTckY8B_Vre5sTj"
              imgCredit="Credit: Iconify"
            />
            <ListDisc :items="list2" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Blush'"
            :link="'https://www.figma.com/community/plugin/838959511417581040/blush'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*uhDL7PcwLehTCegYPAcUmQ.png"
              imgCredit="Credit: Blush"
            />
            <ListDisc :items="list3" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Blobs'"
            :link="'https://www.figma.com/community/plugin/739208439270091369/blobs'"
            />
            <CreditImg 
                imgSrc="https://cdn-images-1.medium.com/max/1600/1*WGQIcNyJGs5VkmUIZgM1eQ.png"
                imgCredit="Credit: Blobs"
              />
              <ListDisc :items="list4" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Stark'"
            :link="'https://www.figma.com/community/plugin/732603254453395948/stark-contrast-accessibility-checker'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*4-RbPRzw9d-KEaiFRPNVZA.png"
              imgCredit="Credit: Stark"
            />
            <ListDisc :items="list5" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Content Reel'"
            :link="'https://www.figma.com/community/plugin/731627216655469013/content-reel'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*jWp4EGG66xY-bXiD.png"
              imgCredit="Credit: Content Reel"
            />
            <ListDisc :items="list6" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Autoflow'"
            :link="'https://www.figma.com/community/plugin/733902567457592893/autoflow'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*Fr1yYRswchP0lYOC.png"
              imgCredit="Credit: Autoflow"
            />
            <ListDisc :items="list7" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Webgradients'"
            :link="'https://www.figma.com/community/plugin/802147585857776440/webgradients'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*d4hQDyPR9eozgOqQ.png"
              imgCredit="Credit: Webgradients"
            />
            <ListDisc :items="list8" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'LottieFiles'"
            :link="'https://www.figma.com/community/plugin/809860933081065308/lottiefiles-create-animations-export-from-figma-to-lottie'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*8zho11wYWPgfJmBsW6GQ6Q.png"
              imgCredit="Credit: LottieFiles"
            />
            <ListDisc :items="list9" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Google Sheets Sync'"
            :link="'https://www.figma.com/community/plugin/735770583268406934/google-sheets-sync'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*EQL_3EDn3ksc6Z_DEoysTA.png"
              imgCredit="Credit: Google Sheets Sync"
            />
            <ListDisc :items="list10" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Wireframe'"
            :link="'https://www.figma.com/community/plugin/742764242781786818/wireframe'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*sk8rCv61XAnxYgwytng7sw.png"
              imgCredit="Credit: Wireframe"
            />
            <ListDisc :items="list11" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Charts'"
            :link="'https://www.figma.com/community/plugin/731451122947612104/charts'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*ziPbuF0VRG0aCmHEDsnYrQ.png"
              imgCredit="Credit: Charts"
            />
            <ListDisc :items="list12" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'額外介紹：Shape Mask'"
            :link="'https://www.figma.com/community/plugin/1420953914431407843/shape-mask'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*VUK2az0HJHzilzN0Rpgv0A.png"
              imgCredit="Credit: Shape Mask"
            />
            <Callout>
              <H3
              :title="'「Shape Mask」是我親自開發的一款 Figma 插件，為了幫助設計師在工作中更加高效地處理遮罩效果，並提供各種無限創意的可能。'"
              class="italic font-normal leading-loose text-center"
              />
            </Callout>
            <ListDisc 
            :items="list13"
            customClass="space-y-4"
            >
              <template #slot-2>
                <ListNum :items="list14" />
              </template>
              <template #slot-3>
                <ListNum :items="list15" />
              </template>
            </ListDisc>
          </div>
          <Mention 
              :showNote="true"
              note="延伸閱讀：開發 Shape Mask Plugin 的過程"
              :link="'/blog/post/18'" 
              :title="'身為 UI/UX 設計師開發的第一個 Figma Plugin - Shape Mask'" 
              :content="'設計師為自己打造，Shape Mask 解決遮罩設計的每個細節困擾！'" 
              :image="'https://cdn-images-1.medium.com/max/1600/1*VUK2az0HJHzilzN0Rpgv0A.png'" 
            />
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
          title: "功能",
          description: "提供免費的高品質圖片素材。",
        },
        {
          title: "適用場景",
          description: "設計中需要真實圖片時，直接插入圖片，無需離開 Figma。",
        },
        {
          title: "亮點",
          description: "圖片資源豐富，支持快速搜索。",
        }
      ],
      list2: [
        {
          title: "功能",
          description: "提供超過 100,000 個開源圖標庫。",
        },
        {
          title: "適用場景",
          description: "快速找到並插入所需的常用圖標，省去自行設計的時間。",
        },
        {
          title: "亮點",
          description: "支持多樣化風格，覆蓋主流設計需求。",
        }
      ],
      list3: [
        {
          title: "功能",
          description: "插入由插畫師創作的可定制插畫。",
        },
        {
          title: "適用場景",
          description: "設計需要插畫元素時，快速選擇合適的素材。",
        },
        {
          title: "亮點",
          description: "插畫風格多樣，可調整顏色和細節。",
        }
      ],
      list4: [
        {
          title: "功能",
          description: "快速創建可自定義的「Blob」形狀（隨機流動、不規則的有機形狀）。",
        },
        {
          title: "適用場景",
          description: "在設計中需要創造有機、抽象形狀時，適合背景、裝飾或獨特的視覺元素。",
        },
        {
          title: "亮點",
          description: "可隨機生成不規則的「Blob」形狀，並且可以調整顏色、尺寸和變化範圍，為設計帶來更多創意選擇。",
        }
      ],
      list5: [
        {
          title: "功能",
          description: "幫助檢查設計的無障礙性。",
        },
        {
          title: "適用場景",
          description: "確保色彩對比和文字可讀性，提升包容性設計。",
        },
        {
          title: "亮點",
          description: "無障礙檢查工具的首選，簡單直觀。",
        }
      ],
      list6: [
        {
          title: "功能",
          description: "快速插入假文案、用戶名和圖片。",
        },
        {
          title: "適用場景",
          description: "為設計添加模擬真實內容，提高展示效果。",
        },
        {
          title: "亮點",
          description: "支持自定義數據集，滿足多樣化需求。",
        }
      ],
      list7: [
        {
          title: "功能",
          description: "自動繪製頁面之間的流程線。",
        },
        {
          title: "適用場景",
          description: "設計用戶流或頁面連結時，快速生成流向線條。",
        },
        {
          title: "亮點",
          description: "操作直觀，提升原型設計效率。",
        }
      ],
      list8: [
        {
          title: "功能",
          description: "提供一系列精美的漸變色背景素材。",
        },
        {
          title: "適用場景",
          description: "設計需要使用色彩過渡或漸變背景時，快速選擇合適的漸變色組合。",
        },
        {
          title: "亮點",
          description: "涵蓋各種漸變色設計風格，並且支持一鍵應用到 Figma 作品中，節省自創顏色的時間。",
        }
      ],
      list9: [
        {
          title: "功能",
          description: "插入和預覽 Lottie 動畫。",
        },
        {
          title: "適用場景",
          description: "在設計中展示動態效果，提升視覺吸引力。",
        },
        {
          title: "亮點",
          description: "支持從 Lottie 社群直接獲取動畫資源。",
        }
      ],
      list10: [
        {
          title: "功能",
          description: "同步 Google Sheets 的數據到 Figma。",
        },
        {
          title: "適用場景",
          description: "設計涉及數據內容時，如表單或動態展示。",
        },
        {
          title: "亮點",
          description: "數據與設計動態聯動，適合數據驅動的項目。",
        }
      ],
      list11: [
        {
          title: "功能",
          description: "快速搭建線框圖。",
        },
        {
          title: "適用場景",
          description: "項目初期需要快速構建低保真原型。",
        },
        {
          title: "亮點",
          description: "提供多種線框元件，幫助快速完成頁面結構設計。",
        }
      ],
      list12: [
        {
          title: "功能",
          description: "創建多種圖表的可視化工具。",
        },
        {
          title: "適用場景",
          description: "設計需要嵌入數據圖表的界面或專案。",
        },
        {
          title: "亮點",
          description: "支持條形圖、折線圖、圓餅圖等多種樣式，可導入 CSV 數據生成。",
        }
      ],
      list13: [
        {
          title: "功能",
          description: "快速套用複雜的形狀遮罩效果，並支持反轉遮罩效果以及自定義形狀上傳。",
        },
        {
          title: "適用場景",
          description: "無論是裁剪遮罩、反轉遮罩還是上傳自定義的形狀遮罩，都能輕鬆實現。",
        },
        {
          title: "亮點"
        },
        {
          title: "使用建議"
        },
        {
          title: "如何使用",
          description: "你只需要選擇要套用遮罩的目標圖層，並點擊插件即可輕鬆應用遮罩效果。你還可以上傳自己的自定義形狀並應用，甚至調整遮罩的反轉效果，以滿足各種設計需求。",
        },
      ],
      list14: [
        {
          title: "反轉遮罩效果",
          description: "除了基本的遮罩功能，Shape Mask 還支持反轉遮罩效果，擴展了設計的靈活性。",
        },
        {
          title: "自定義遮罩形狀",
          description: "用戶可以上傳自定義形狀作為遮罩，你可以親自設計特別的 svg 形狀，並應用於你的設計之中。",
        },
        {
          title: "提供簡單直觀的操作界面",
          description: "以各種形狀風格做為分類篩選，用戶可以快速找到適合的形狀並套用，點擊切換按鈕馬上反轉遮罩效果。",
        }
      ],
      list15: [
        {
          description: "如果你經常需要創建精細的遮罩效果、需要反轉遮罩或處理不同形狀的遮罩，這款外掛將大幅提升你的設計流程。",
        },
        {
          description: "無論是創建高質感的圖像裁剪，還是設計需要創意遮罩效果的特殊視覺元素，Shape Mask 都能幫助你實現。",
        }
      ],
      list16: [
        {
          description: "如果你經常需要創建精細的遮罩效果、需要反轉遮罩或處理不同形狀的遮罩，這款外掛將大幅提升你的設計流程。",
        },
        {
          description: "無論是創建高質感的圖像裁剪，還是設計需要創意遮罩效果的特殊視覺元素，Shape Mask 都能幫助你實現。",
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
  created() {
    // Fetch or set posts data here if needed
  }
};
</script>