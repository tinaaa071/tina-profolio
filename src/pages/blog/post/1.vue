<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*LSgS3r0VigNdsXHxAx9kqg.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item2'),
          date: '2024．09．02',
          title: '介面設計原則：打造用戶友好體驗的基石',
          desc: '設計以用戶為中心，創造流暢且愉悅的數位體驗！',
          brief: '介面設計不僅僅是讓一個產品「看起來漂亮」，更是影響用戶體驗和產品成功的關鍵因素。',
          menu: [
            { menu: '清晰性優先' },
            { menu: '以用戶為中心' },
            { menu: '最少的認知負荷' },
            { menu: '給予即時反饋' },
            { menu: '美感與實用性並重' },
            { menu: '包容性與可及性' },
            { menu: '結語' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        @navigate="scrollToSection" 
        />
        <Content>
          <div class="flex flex-col gap-4" id="section1">
            <H1 
            :title="'1. 清晰性優先'"
            />
            <p>
              用戶在互動過程中不應感到困惑。設計時，確保每個元素都能清楚地傳達其功能和用途。
            </p>
            <ListDisc :items="list1" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*04H7pOnW09DS-dEX"
              imgCredit="Credit: Figma"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'2. 以用戶為中心'"
            />
            <p>
              了解目標用戶的需求與行為模式是設計的起點。
            </p>
            <ListDisc :items="list2" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*g2ruZ1wlf2Gwec-TktYGyw.png"
              imgCredit="Credit: Figma"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'3. 最少的認知負荷'"
            />
            <p>
              人類的短期記憶有限，設計應盡量減少用戶需要記住的資訊量。
            </p>
            <ListDisc :items="list3" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*Egpod5rXCN4nSIZ74CheOw.png"
              imgCredit="Credit: Figma"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'4. 給予即時反饋'"
            />
            <p>
              用戶在操作後希望立即得到回應，無論成功或失敗。
            </p>
            <ListDisc :items="list4" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'5. 美感與實用性並重'"
            />
            <p>
              美觀的設計不僅吸引目光，更能讓用戶感到舒適，從而提升使用意願。
            </p>
            <ListDisc :items="list5" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*0szhVQkcv40QHHOeB6VXAQ.png"
              imgCredit="Credit: Figma"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section6">
            <H1 
            :title="'6. 包容性與可及性'"
            />
            <p>
              確保所有人都能方便地使用產品，包括有特殊需求的用戶。
            </p>
            <ListDisc :items="list6" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section7">
            <H1 
            :title="'結語'"
            />
            <p>
              介面設計是一門平衡藝術，既要滿足用戶需求，又要體現品牌價值。成功的設計不僅能提升用戶體驗，更能為產品贏得市場競爭力。
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
          title: "簡單明瞭的語言",
          description: "使用簡單的文字，避免行業術語或模糊的描述。",
        },
        {
          title: "一致性設計",
          description: "確保標籤、圖標和操作在整個介面中具有一致性。",
        },
        {
          title: "資訊分層",
          description: "將資訊按照優先級分層顯示，避免讓用戶一次接收到過多內容。",
        }
      ],
      list2: [
        {
          title: "用戶研究",
          description: "通過訪談、觀察和數據分析了解用戶需求。",
        },
        {
          title: "可用性測試",
          description: "迭代設計並持續測試，找出痛點並進行改進。",
        },
        {
          title: "適應性設計",
          description: "針對不同裝置（如手機、平板和桌面）提供最佳化的使用體驗。",
        }
      ],
      list3: [
        {
          title: "提供清晰的提示",
          description: "例如顯示進度條或上下文說明。",
        },
        {
          title: "避免重複輸入",
          description: "儘可能預填表單或保存用戶數據，減少重複操作。",
        },
        {
          title: "直觀的導航",
          description: "用戶應能快速找到他們需要的功能或內容。",
        }
      ],
      list4: [
        {
          title: "視覺反饋",
          description: "例如按鈕被點擊後變色，表明操作已經完成。",
        },
        {
          title: "錯誤處理",
          description: "如果出現錯誤，提供清楚的訊息和解決方案，而不是讓用戶感到迷茫。",
        }
      ],
      list5: [
        {
          title: "簡約設計",
          description: "避免過多的裝飾元素，保持設計的簡潔。",
        },
        {
          title: "色彩和排版",
          description: "選擇易於閱讀的字體，並運用對比來強調重點內容。",
        },
        {
          title: "一致的品牌風格",
          description: "確保設計風格與品牌調性一致，增強辨識度。",
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
          // date: new Date().toLocaleDateString(),
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