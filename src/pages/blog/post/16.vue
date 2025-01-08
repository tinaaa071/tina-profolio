<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*OT0pTyXTOhQ2tuQzuqSwwg.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item3'),
          date: '2024．11．29',
          title: 'UI/UX Designer 也要會寫程式嗎？',
          desc: '設計師是否需要程式技能？了解基礎，為創意加分！',
          brief: '在設計領域，特別是 UI/UX 設計中，是否需要掌握程式設計技能一直是一個熱門話題。有人認為設計師應該專注於設計本身，而有人則認為學會寫程式能夠提升設計的價值與效率。那麼，UI/UX 設計師到底需不需要會寫程式？',
          menu: [
            { menu: '設計師的核心技能：設計思維' },
            { menu: '程式設計的附加價值' },
            { menu: '不會寫程式的設計師有出路嗎？' },
            { menu: '結論：是否要學程式視需求而定' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        @navigate="scrollToSection" 
        />
        <Content>
          <div class="flex flex-col gap-4" id="section1">
            <H1 
            :title="'設計師的核心技能：設計思維'"
            />
            <p>
              UI/UX 設計師的主要職責是創建直觀且易用的介面，並解決用戶的需求。他們需要擁有：
            </p>
            <ListDisc :items="list1" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'程式設計的附加價值'"
            />
            <p>
              雖然程式設計不是 UI/UX 設計師的必備技能，但在某些情況下，掌握程式語言可能會帶來明顯的優勢：
            </p>
            <ListNum :items="list2" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'不會寫程式的設計師有出路嗎？'"
            />
            <p>
              當然有。許多優秀的 UI/UX 設計師並不擅長程式，但依然能夠創造出色的產品。重點在於他們如何與團隊合作，以及如何專注於用戶需求和設計本質。如果你不想學程式，以下幾點是關鍵：
            </p>
            <ListDisc :items="list3" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'結論：是否要學程式視需求而定'"
            />
            <p>
              UI/UX 設計師是否需要會寫程式，取決於你的職涯目標與工作環境：
            </p>
            <ListDisc :items="list4" />
            <p>
              程式設計不是 UI/UX 設計師的必備能力，但它是一項能夠擴展職業可能性的附加技能。作為設計師，最重要的是始終聚焦於如何為用戶帶來更好的體驗，而非被技能清單所限制。
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
          title: "用戶研究能力",
          description: "了解用戶的痛點和需求。",
        },
        {
          title: "視覺設計能力",
          description: "設計出美觀且實用的介面。",
        },
        {
          title: "信息架構能力",
          description: "組織內容以提升可用性。",
        },
        {
          title: "原型設計能力",
          description: "使用工具如 Figma 或 Sketch，快速構建和測試設計。",
        }
      ],
      list2: [
        {
          title: "提升設計實現的可行性",
          description: "理解程式基礎（如 HTML、CSS、JavaScript）可以幫助設計師更清楚設計如何在實際的開發環境中被實現，避免不切實際的設計。",
        },
        {
          title: "促進與開發團隊的溝通",
          description: "設計與開發常常需要緊密合作，懂一些程式設計的語言，能讓設計師更有效地與開發人員交流，例如討論技術限制或實現細節。",
        },
        {
          title: "加速原型開發",
          description: "一些工具（如 Framer、Webflow）需要基本的程式知識，設計師可以快速構建具交互功能的高保真原型，提升用戶測試的效率。",
        },
        {
          title: "增加職業競爭力",
          description: "在某些小型團隊或初創公司中，UI/UX 設計師可能需要兼顧部分前端開發的工作，這時程式技能就成了加分項。",
        }
      ],
      list3: [
        {
          description: "深入了解設計工具（如 Figma、Adobe XD）以提升效率。",
        },
        {
          description: "學習設計交付標準，確保開發團隊能輕鬆解讀你的設計。",
        },
        {
          description: "磨練溝通技巧，與開發團隊緊密合作，橋接設計與技術的差距。",
        }
      ],
      list4: [
        {
          description: "如果你在大型企業工作，設計與開發通常是分工明確的，程式技能的需求可能較低。",
        },
        {
          description: "如果你在初創公司，或希望成為全能型設計師（T 型人才），那麼學習一些程式技能可能會是明智的選擇。",
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