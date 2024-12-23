<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*GxGNHeVOgVS_SFqGdY3TfQ.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item2'),
          date: '2024．09．17',
          title: '使用 Storybook 構建你的設計系統',
          desc: 'Storybook：讓你的設計系統輕鬆維護與共享',
          brief: '在 UI/UX 設計工作中，構建一個準確而健固的設計系統，是確保用戶體驗的重要一環。',
          menu: [
            { menu: '什麼是 Storybook？' },
            { menu: 'Storybook 在設計系統中的角色' },
            { menu: 'Storybook 的主要功能' },
            { menu: '如何開始使用 Storybook 建立設計系統' },
            { menu: 'Storybook 與設計工具的整合' },
            { menu: '如何維護和擴展設計系統' },
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
            :title="'什麼是 Storybook？'"
            />
            <p>
              Storybook 是一個開源的 UI 開發環境，用於構建、開發和測試 UI 元件。它可以幫助團隊建立可重複使用的 UI 元件庫，並且能夠將這些元件以視覺化的方式呈現。對於 UI/UX 設計師來說，Storybook 不僅是展示元件的工具，更是協助設計系統維護的橋樑。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'Storybook 在設計系統中的角色'"
            />
            <p>
              設計系統的核心是確保一致性，無論是在界面設計還是開發過程中。Storybook 為設計師提供了一個集中管理元件的場所，能夠將 UI 元件與樣式指南結合，並實現即時更新。這不僅有助於設計師在設計過程中確認元件的視覺一致性，也能確保開發團隊使用的元件符合設計要求。
            </p>
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*pSGF7fivZ6I3RHsM.png"
              imgCredit="Credit: Storybook"
              aspectRatio="aspect-auto"
            />
          </div>
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'Storybook 的主要功能'"
            />
            <ListDisc :items="list1" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*ZCQGHOKQfhrvWWDM.jpg"
              imgCredit="Credit: Storybook"
              aspectRatio="aspect-auto"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'如何開始使用 Storybook 建立設計系統'"
            customClass="space-y-4"
            />
            <p>
              建立設計系統的第一步是將常用的 UI 元件收集並在 Storybook 中構建一個元件庫。以下是簡單的步驟：
            </p>
            <ListNum 
            :items="list2"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'Storybook 與設計工具的整合'"
            customClass="space-y-4"
            />
            <p>
              雖然 Storybook 是為開發人員設計的工具，但它與設計工具（如 Figma 或 Sketch）也能夠很好地配合工作。設計師可以在 Figma 中設計 UI 元件，然後將這些設計轉化為 Storybook 元件，確保設計與開發之間的一致性。這樣的工作流程能大大提高設計和開發之間的協作效率，避免設計偏差和錯誤。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section6">
            <H1 
            :title="'如何維護和擴展設計系統'"
            customClass="space-y-4"
            />
            <p>
              隨著產品的發展，設計系統會不斷擴展和調整。在 Storybook 中維護設計系統相對簡單，因為它的元件庫結構清晰，容易擴展。每當新增或修改元件時，設計師只需更新 Storybook 中的相應故事，並確保所有團隊成員都能及時查看和使用最新的元件。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section7">
            <H1 
            :title="'結語'"
            />
            <p>
              使用 Storybook 建立設計系統，對於 UI/UX 設計師來說，不僅能夠提升設計與開發的協作效率，還能確保產品的一致性和高品質。無論是構建元件、維護設計系統，還是與團隊協作，Storybook 都能提供強大的支持。透過 Storybook，我們可以創建一個可持續發展的設計系統，並在整個開發過程中保持一致的使用體驗。
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
          title: "視覺化元件庫",
          description: "Storybook 提供了一個瀏覽元件的界面，讓設計師可以直接檢視每個元件的狀態和樣式，快速檢查設計的準確性。",
        },
        {
          title: "元件的獨立開發與測試",
          description: "開發人員可以在 Storybook 中單獨開發和測試元件，而不需要依賴完整的應用程式運行環境。",
        },
        {
          title: "自訂擴展",
          description: "Storybook 支援許多插件，設計師可以利用這些插件來增加設計檢視功能，例如視覺測試工具、色彩檢查、可訪問性測試等。",
        },
        {
          title: "團隊協作",
          description: "Storybook 提供了與開發人員的高效協作方式，設計師和開發人員可以在同一平台上查看、測試和修改元件，避免了傳統設計工具和開發工具之間的隔閡。",
        }
      ],
      list2: [
        {
          title: "安裝 Storybook",
          description: "使用 npm 或 yarn 安裝 Storybook，並進行必要的設定。",
        },
        {
          title: "創建元件",
          description: "在你的應用程式中創建可重複使用的 UI 元件（例如按鈕、表單、卡片等），並將它們引入 Storybook 中。",
        },
        {
          title: "編寫故事",
          description: "為每個元件創建 stories，這些故事將展示不同狀態下的元件，例如預設狀態、點擊狀態、禁用狀態等。",
        },
        {
          title: "共享與協作",
          description: "一旦設置完成，你可以與開發團隊共享 Storybook，讓大家可以即時查看、測試和使用這些元件。",
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