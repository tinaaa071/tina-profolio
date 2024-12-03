<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/0*YBzjF3NbL3ATmRch.png',
          credit: 'Credit: lottiefiles',
          category: $t('blog.item2'),
          date: '2024．11．03',
          title: 'LottieFiles：讓動畫設計與開發無縫接軌的革命性工具',
          desc: '從設計到程式，一鍵搞定，LottieFiles 為動畫賦能！',
          menu: [
            { menu: '什麼是 LottieFiles？' },
            { menu: 'LottieFiles 的核心功能' },
            { menu: '為什麼選擇 LottieFiles？' },
            { menu: '如何使用 LottieFiles？' },
            { menu: '結語' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        >
          <template #brief>
            <p>
              LottieFiles 作為一個專注於動畫的解決方案，為設計師與開發者之間搭建了一座高效的橋樑。
            </p>
          </template>
        </Brief>
        <Content>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'什麼是 LottieFiles？'"
            />
            <p>
              LottieFiles 是一個專注於 Lottie 動畫的生態系統，提供了大量免費或付費的動畫資源、工具和開發支援。從設計到開發，LottieFiles 為設計師和開發者提供了一站式解決方案，讓動畫的應用變得前所未有的簡單。
            </p>
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*6M6--LA4uZqDQb8M.png"
              imgCredit="Credit: lottieFiles"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'LottieFiles 的核心功能'"
            />
            <ListNum :items="list1" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*b02P_QFpES32o0LI"
              imgCredit="Credit: lottieFiles"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'為什麼選擇 LottieFiles？'"
            />
            <ListDisc :items="list2" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'如何使用 LottieFiles？'"
            />
            <ListDisc :items="list3" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*fMyKryGEjzZMBrrc.png"
              imgCredit="Credit: lottieFiles"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'結語'"
            />
            <p>
              LottieFiles 為用戶提供了簡單、直觀的使用體驗，無論是下載現成動畫、進行自訂，還是快速整合到項目中，都非常方便。
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
          title: "海量動畫庫",
          description: "LottieFiles 提供了數千個免費與高品質的動畫，涵蓋多種主題與用途。無論是網站圖標、App 動效，還是社交媒體內容，總能找到適合的動畫。",
        },
        {
          title: "瀏覽器即時預覽",
          description: "設計師可以將 After Effects 製作的動畫通過 Bodymovin 外掛導出為 Lottie 格式，並直接在 LottieFiles 平台上進行預覽與測試，免去反覆導入開發環境的麻煩。",
        },
        {
          title: "團隊協作與版本控制",
          description: "LottieFiles 提供協作功能，讓團隊成員能輕鬆分享動畫文件，並進行版本管理，避免文件錯亂或重複工作。",
        },
        {
          title: "開發者友好的整合",
          description: "LottieFiles 為各種開發框架（如 React、Flutter、iOS 和 Android）提供開箱即用的整合工具與文件，讓開發者快速上手。",
        }
      ],
      list2: [
        {
          title: "節省開發時間",
          description: "設計師與開發者能夠高效協作，縮短開發周期。",
        },
        {
          title: "提升性能",
          description: "Lottie 動畫比傳統 GIF 文件更小、更流暢，且支持向量圖形，無損放大。",
        },
        {
          title: "簡化工作流程",
          description: "從設計到上線，LottieFiles 簡化了每一個環節，降低學習曲線。",
        }
      ],
      list3: [
        {
          title: "下載 Lottie 文件",
          description: "在動畫詳情頁面中，點擊 Download JSON 按鈕即可下載 Lottie 動畫文件（JSON 格式）。",
        },
        {
          title: "複製 URL",
          description: "如果你不想下載文件，也可以選擇直接複製動畫的 URL。這對於開發者來說非常便利，因為可以直接在代碼中使用這個遠端的動畫文件。",
        },
        {
          title: "整合到應用",
          description: "參考官方文檔，將 Lottie 動畫無縫嵌入網站或 App 中。",
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