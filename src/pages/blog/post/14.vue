<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*XmqGmjWlFW0ZdY8xyTCGqA.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item2'),
          date: '2024．11．08',
          title: 'Bento Grid UI：靈感來自便當盒的介面設計風格',
          desc: '靈感來自便當，創造視覺與功能的完美平衡',
          brief: '為什麼 Bento Grid 成為設計師的新寵？這篇文章帶你深入了解這種介面設計風格，如何結合簡潔性與功能性，打造視覺與使用體驗的雙重盛宴。',
          menu: [
            { menu: 'Bento Grid 是什麼？' },
            { menu: 'Bento Grid 的優勢' },
            { menu: 'Bento Grid 的應用場景' },
            { menu: '如何設計出優秀的 Bento Grid UI？' },
            { menu: 'Bento Grid 的設計挑戰' },
            { menu: '總結' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        @navigate="scrollToSection" 
        />
        <Content>
          <p>
            我們的日常生活充滿設計的可能性，而「Bento Grid」這一設計風格正是從最平凡的便當盒中發掘出的靈感。便當盒不僅是一個盛裝食物的工具，它的分格設計、色彩搭配，以及對整體性的追求，都讓它成為了功能與美學結合的經典案例。
          </p>
          <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*zzvXsCCag1QzOhtY"
            />
          <div class="flex flex-col gap-4" id="section1">
            <H1 
            :title="'Bento Grid 是什麼？'"
            />
            <div>
              <span>關鍵特徵：</span>
              <ListDisc :items="list1" />
            </div>
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*O_XtwR4KLlgl-jpp.jpg"
              imgCredit="Credit: Apple"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'Bento Grid 的優勢'"
            />
            <ListNum :items="list2" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*K3cvsFYIA2OZ8JDQ.jpeg"
              imgCredit="Credit: Apple"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'Bento Grid 的應用場景'"
            />
            <ListNum :items="list3" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*kZsEPxW_2O63m29n.png"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'如何設計出優秀的 Bento Grid UI？'"
            />
            <ListNum :items="list4" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'Bento Grid 的設計挑戰'"
            />
            <p>
              儘管 Bento Grid 設計風格有許多優點，但也有需要注意的挑戰：
            </p>
            <ListDisc :items="list5" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section6">
            <H1 
            :title="'總結'"
            />
            <p>
              Bento Grid UI 將結構性美感與實用性完美結合，是現代介面設計中備受推崇的風格之一。不論是個人作品集還是大型資訊平台，都能從中找到靈感與實用價值。
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
          title: "區塊化排列",
          description: "內容分隔成獨立區塊，各自有清晰的邊界。",
        },
        {
          title: "對稱性與均衡感",
          description: "設計重視視覺上的對稱與比例。",
        },
        {
          title: "模組化設計",
          description: "每個區塊可以單獨設計或替換，靈活性高。",
        }
      ],
      list2: [
        {
          title: "提升用戶體驗",
          description: "Bento Grid 的清晰結構讓用戶可以快速找到所需內容，減少認知負擔。例如，在電商網站中，產品信息可以按分類顯示，提升瀏覽效率。",
        },
        {
          title: "易於適應響應式設計",
          description: "這種風格天然適合多設備顯示，無論在手機、平板還是桌面設備上，內容都能以均衡方式呈現。",
        },
        {
          title: "強調視覺吸引力",
          description: "井然有序的設計風格能為介面帶來專業感與美感，尤其適合以圖片或內容為主的網站，例如作品集、部落格或展示頁面。",
        }
      ],
      list3: [
        {
          title: "作品集網站",
          description: "設計師、攝影師等創意工作者的作品展示，利用區塊劃分來強調每個作品的獨特性。",
        },
        {
          title: "電商平台",
          description: "以網格顯示產品卡片，方便用戶快速篩選並瀏覽。",
        },
        {
          title: "資訊平台或部落格",
          description: "內容分類顯示（如熱門文章、最新消息、主題標籤），讓用戶更容易掌握重點資訊。",
        }
      ],
      list4: [
        {
          title: "選擇適合的網格系統",
          description: "從 4 列、6 列或 12 列網格系統開始，確保內容在不同螢幕尺寸下都能保持一致性。",
        },
        {
          title: "利用間距與留白",
          description: "適當的留白不僅增強可讀性，也能提升整體美感。",
        },
        {
          title: "結合動態效果",
          description: "區塊之間的滑動、縮放或切換效果能增加互動性，讓設計更具吸引力。",
        }
      ],
      list5: [
        {
          title: "避免內容過於切割",
          description: "過多的區塊可能讓設計顯得碎片化，需注意整體流暢性。",
        },
        {
          title: "兼顧功能性與美感",
          description: "過度注重視覺排列可能忽略了用戶需求。",
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