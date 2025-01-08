<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*Y8yyZ7mfWqM9DkBiEMyJQg.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item4'),
          date: '2024．09．02',
          title: '打造精美的 UI 設計：必備資源與工具',
          desc: '設計精美介面，必備資源讓創意無限延伸！',
          brief: '一個好的 UI 不僅能吸引使用者，更能提升使用者體驗（UX）。作為設計師，掌握豐富的設計資源是創造成功作品的關鍵',
          menu: [
            { menu: 'UI 設計靈感來源' },
            { menu: '免費 Icon 資源' },
            { menu: '免費圖庫網站' },
            { menu: '插畫與創意素材' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        @navigate="scrollToSection"
        />
        <Content>
          <div class="flex flex-col gap-4" id="section1">
            <H1 
            :title="'UI 設計靈感來源'"
            />
            <ListNum :items="list1" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*olrafDizevJ6buKG.jpg"
              imgCredit="Credit: Awwwards"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'免費 Icon 資源'"
            />
            <ListNum :items="list2" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*N1GHwJwKCd51pM8E66Hnug.png"
              imgCredit="Credit: Icons8"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'免費圖庫網站'"
            />
            <ListNum :items="list3" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*hQ95Sg6h6RbbDi4_MQFaag.png"
              imgCredit="Credit: Unsplash"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'插畫與創意素材'"
            />
            <ListNum :items="list4" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*6ZbZDTdX71H_XtKh.jpg"
              imgCredit="Credit: blush"
            />
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
          title: "Behance",
          description: "Adobe 提供的設計社群，這裡匯聚了來自全球設計師的優秀作品，無論是 UI/UX 設計、平面設計，還是插畫，你都能找到靈感。",
          link: 'https://www.behance.net/'
        },
        {
          title: "Dribbble",
          description: "另一個備受歡迎的設計分享平台。常常作為 UI 設計師的展示與創作平台，可以在此發現很多具有創意的 UI 設計項目。",
          link: 'https://dribbble.com/'
        },
        {
          title: "Awwwards",
          description: "專注於網站設計，展示全球最優秀的網站 UI 設計案例，非常適合尋求網站設計靈感的設計師。",
          link: 'https://www.awwwards.com/'
        },
        {
          title: "Mobbin",
          description: "提供豐富的移動應用設計範例，涵蓋熱門應用的 UI 流程與元件。特別適合尋找 App 設計靈感。",
          link: 'https://mobbin.com/browse/ios/screens'
        },
        {
          title: "Collect UI",
          description: "專注於精選的 UI 設計作品，涵蓋登錄頁面、表單、按鈕等各類設計，方便快速獲取靈感。",
          link: 'https://collectui.com/'
        },
        {
          title: "Pinterest",
          description: "靈感無限的視覺平台，可以輕鬆收藏與探索各類設計風格的範例。",
          link: 'https://www.pinterest.com/'
        },
      ],
      list2: [
        {
          title: "Icons8",
          description: "提供了豐富的圖標、插圖與照片，支援自定義樣式與下載。",
          link: 'https://icons8.com/'
        },
        {
          title: "Flaticon",
          description: "提供超過數百萬個免費圖標，可作為單個文件下載或以圖標包形式使用。",
          link: 'https://www.flaticon.com/'
        },
        {
          title: "Material Icons",
          description: "Google 提供的免費圖標資源，遵循 Material Design 規範。",
          link: 'https://fonts.google.com/icons'
        }
      ],
      list3: [
        {
          title: "Unsplash",
          description: "提供高質量的免費圖片，是設計作品中的背景或配圖首選。",
          link: 'https://unsplash.com/'
        },
        {
          title: "Pexels",
          description: "提供數十萬張高品質免費圖片和影片，適合多種用途。",
          link: 'https://www.pexels.com/zh-tw/'
        },
        {
          title: "Pixabay",
          description: "提供免版權的圖片、插圖、向量圖和影片。",
          link: 'https://pixabay.com/'
        },
        {
          title: "Freepik",
          description: "提供圖片、插圖、向量圖和 PSD 模板資源，部分資源需要署名。",
          link: 'https://www.freepik.com/'
        }
      ],
      list4: [
      {
          title: "Blush",
          description: "提供高質量的插畫素材，可自定義角色和配色。",
          link: 'https://blush.design/'
        },
        {
          title: "Humaaans",
          description: "提供可自定義的人物插畫，適合展示頁設計。",
          link: 'https://humaaans.com/'
        },
        {
          title: "unDraw",
          description: "提供免費開源的 SVG 插圖，適合網站和應用程式設計。",
          link: 'https://undraw.co/illustrations'
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