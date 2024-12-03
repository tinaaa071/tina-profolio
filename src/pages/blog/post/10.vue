<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/0*nGEzJ1WU_0eop9iQ.gif',
          credit: 'Credit: lottiefiles',
          category: $t('blog.item2'),
          date: '2024．11．02',
          title: 'Lottie 動畫：打造更輕量、更高效的互動體驗',
          desc: '打造高效互動體驗，Lottie 是你的最佳選擇！',
          menu: [
            { menu: '什麼是 Lottie？' },
            { menu: 'Lottie 的應用場景' },
            { menu: '如何開始使用 Lottie？' },
            { menu: '成功案例分享' },
            { menu: '總結' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        >
          <template #brief>
            <p>
              在現今數位時代，動畫不僅是一種視覺效果，更是一種有效的溝通工具。無論是行動應用程式、網站，還是行銷活動，動畫都能提升用戶體驗。然而，傳統的動畫製作和導入方式常常伴隨著效能瓶頸與檔案過大的問題。這時候，Lottie 成為了解決方案。
            </p>
          </template>
        </Brief>
        <Content>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'什麼是 Lottie？'"
            />
            <p>
              Lottie 是一種開源動畫格式，由 Airbnb 的工程團隊開發。它可以將設計師使用 Adobe After Effects 製作的動畫，透過 Bodymovin 插件匯出成 JSON 格式，並直接嵌入到應用程式或網站中。
              <br>
              這種格式的優勢在於：
            </p>
            <ListDisc :items="list1" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*1yVRwSSqxYr-K63j.png"
              imgCredit="Credit: lottiefiles"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Lottie 的應用場景'"
            />
            <ListNum :items="list2" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'如何開始製作 Lottie？'"
            />
            <ListNum 
            :items="list3"
            customClass="space-y-4"
            >
              <template #slot-0>
                <Mention 
                  class="mt-4"
                  :showTitle="false"
                  :link="'https://airbnb.io/lottie/#/supported-features'" 
                  :title="'Lottie Docs'" 
                  :content="'Lottie is a mobile library for Web, and iOS that parses Adobe After Effects animations exported as json with Bodymovin and renders them natively on mobile!'" 
                  :image="'https://cdn.iconscout.com/icon/free/png-256/free-lottiefiles-logo-icon-download-in-svg-png-gif-file-formats--lottifiles-brand-iconscout-pack-logos-icons-4674920.png?f=webp'" 
                />
              </template>
              <template #slot-1>
                <ListDisc :items="list4" />
              </template>
            </ListNum>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'成功案例分享'"
            />
            <p>
              Lottie 已被許多知名公司採用，例如：
            </p>
            <ListDisc :items="list5" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'總結'"
            />
            <p>
              UI/UX Lottie 為設計師與開發者提供了一個橋樑，使動畫設計能夠無縫地整合到產品中。透過 Lottie，我們能以輕量的方式提升用戶體驗，並創造更多元的互動可能性。
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
          title: "輕量化",
          description: "Lottie 動畫是基於向量的，因此檔案大小遠小於傳統的 GIF 或影片。",
        },
        {
          title: "跨平台支持",
          description: "支持 iOS、Android、Web 和 React Native 等多個平台。",
        },
        {
          title: "高度可調",
          description: "可以輕鬆修改動畫的顏色、速度，甚至讓動畫具備互動性。",
        }
      ],
      list2: [
        {
          title: "提升用戶界面互動性",
          description: "Lottie 動畫非常適合用於按鈕、過渡效果和載入動畫。比起靜態的 GIF，Lottie 不僅更流暢，也更具視覺吸引力。",
        },
        {
          title: "行銷與品牌推廣",
          description: "動畫可以更有效地傳遞品牌訊息。例如，在產品介紹頁面上，Lottie 動畫可以展示產品功能，增強用戶的理解力與記憶點。",
        },
        {
          title: "創造個性化體驗",
          description: "透過互動式 Lottie 動畫，你可以根據用戶的行為觸發特定動畫，為用戶打造專屬的體驗。",
        }
      ],
      list3: [
        {
          title: "設計階段",
          description: "首先，在 Adobe After Effects 製作動畫，並使用 Bodymovin 插件將動畫匯出為 Lottie 的 JSON 檔案。",
        },
        {
          title: "開發整合",
          description: "接下來，開發者可以使用 Lottie 的各種 SDK，將 JSON 檔案嵌入到應用中。以下是一些常用的資源：",
        },
        {
          title: "優化與測試",
          description: "測試動畫在不同裝置上的表現，並確保效能最佳化。同時，設計師和開發者可以共同微調動畫的細節。",
        }
      ],
      list4: [
        {
          title: "Lottie iOS",
          link: "https://github.com/airbnb/lottie-ios",
        },
        {
          title: "Lottie Android",
          link: "https://medium.com/r?url=https%3A%2F%2Fgithub.com%2Fairbnb%2Flottie-android",
        },
        {
          title: "Lottie Web",
          link: "https://github.com/airbnb/lottie-web",
        }
      ],
      list5: [
        {
          title: "Uber",
          description: "在應用程式中使用 Lottie 來優化載入體驗。",
        },
        {
          title: "Duolingo",
          description: "利用 Lottie 動畫創造更有趣的學習界面。",
        },
        {
          title: "Netflix",
          description: "應用於內部產品和行銷頁面，提升品牌形象。",
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