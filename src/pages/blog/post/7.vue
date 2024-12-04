<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*yJi3pvZRfffeHToNDhtSmQ.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item3'),
          date: '2024．10．20',
          title: '從零開始成為 UI/UX 設計師：自學路徑指南',
          desc: '零基礎也能成設計高手，探索 UI/UX 的學習秘訣！',
          brief: '隨著數位產品需求的增加，UI/UX 設計師成為了一個炙手可熱的職業。不過，對於那些沒有相關背景的人來說，如何自學成為一名合格的設計師是一個常見的問題。',
          menu: [
            { menu: '了解 UI/UX 設計的核心概念' },
            { menu: '學習設計工具' },
            { menu: '培養設計思維' },
            { menu: '建立作品集' },
            { menu: '理解網頁設計的基礎' },
            { menu: '持續學習與進步' },
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
            :title="'了解 UI/UX 設計的核心概念'"
            />
            <p>
              在開始學習之前，你需要了解 UI 和 UX 的差異以及它們如何協作。以下是一些關鍵點：
            </p>
            <ListDisc :items="list1" />
            <CreditImg 
              imgSrc="https://static.ditdot.hr/images/info/ux-ui/ux-ui-00.png"
            />
            <p>
              建議閱讀一些基礎書籍或文章來打好基礎，例如：
            </p>
            <ListDisc :items="list2" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'學習設計工具'"
            />
            <p>
              掌握工具是設計師的必備技能，以下是常用的設計工具：
            </p>
            <ListDisc :items="list3" />
            <CreditImg 
              imgSrc="https://cdn.sanity.io/images/599r6htc/regionalized/db87f4fdef30b6d57c9d432c3eca5dfcbf421cd4-3840x2160.png?w=3840&h=2160&q=75&fit=max&auto=format"
              imgCredit="Credit: Figma"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'培養設計思維'"
            />
            <p>
              設計並不僅僅是美化介面，還需要理解使用者需求與解決問題。以下是幾個提升設計思維的方法：
            </p>
            <ListDisc :items="list4" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'建立作品集'"
            />
            <p>
              作品集是求職過程中的關鍵，以下是建立作品集的建議：
            </p>
            <ListDisc :items="list5" />
            <CreditImg 
              imgSrc="https://miro.medium.com/v2/resize:fit:2000/1*hYiXVLbrGWGsr5xBoWamRw.png"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'理解網頁設計的基礎'"
            />
            <p>
              了解程式語言（如 HTML、CSS 和 JavaScript）能幫助設計師與開發團隊更順暢地溝通。你可以：
            </p>
            <ListDisc :items="list6" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section6">
            <H1 
            :title="'持續學習與進步'"
            />
            <ListDisc :items="list7" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section7">
            <H1 
            :title="'結語'"
            />
            <p>
              自學成為 UI/UX 設計師需要耐心和持續努力，只要掌握正確的學習策略，實踐設計技能並持續吸收新知識，相信你也可以在這個領域取得成功。
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
          title: "UI（User Interface）",
          description: "專注於介面的外觀，包括顏色、排版、圖標和整體視覺設計。",
        },
        {
          title: "UX（User Experience）",
          description: "關注使用者如何與產品互動，包括流程、易用性和滿意度。",
        }
      ],
      list2: [
        {
          description: "《Don't Make Me Think》 by Steve Krug",
        },
        {
          description: "《The Design of Everyday Things》 by Don Norman",
        }
      ],
      list3: [
        {
          title: "Figma",
          description: "當前最受歡迎的線上協作設計工具，適合 UI 設計與原型製作。",
        },
        {
          title: "Sketch",
          description: "Mac 專屬的設計軟體，適合建立高保真設計。",
        },
        {
          title: "Adobe XD",
          description: "Adobe 提供的一站式設計工具。",
        }
      ],
      list4: [
        {
          description: "學習設計流程，例如使用者調研、競品分析、流程圖繪製、低保真原型等。",
        },
        {
          description: "參加線上設計挑戰，如 Daily UI Challenge。",
        },
        {
          description: "研究成功的產品，分析它們的設計細節。",
        }
      ],
      list5: [
      {
          title: "選擇題材",
          description: "可以模仿真實案例或創作自己的產品設計概念。",
        },
        {
          title: "展示過程",
          description: "不僅要展示最終成果，還需要展現你的設計過程，包括思考邏輯、解決方案和迭代過程。",
        },
        {
          title: "保持簡潔",
          description: "選擇 3–5 個高質量的專案即可。",
        }
      ],
      list6: [
        {
          title: "提供可實現的設計方案",
          description: "了解技術限制，避免提出開發難度過高的設計。",
        },
        {
          title: "加速開發過程",
          description: "設計師可以直接提供符合技術規範的建議，減少迭代次數。",
        }
      ],
      list7: [
        {
          description: "閱讀設計 blog 和趨勢文章，例如 Medium 上的 UX Collective。",
        },
        {
          description: "加入設計師社群，參加線上或線下的設計工作坊與分享會。",
        },
        {
          description: "不斷優化你的作品集，讓它反映出你的最新技能。",
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