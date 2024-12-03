<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*hbzy5hAo2iubtbZ5u8gHNg.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item5'),
          date: '2024．11．05',
          title: '《底層邏輯》 - 看清這個世界的底牌',
          desc: '破解世界運行密碼，構建自己的成功法則',
          menu: [
            { menu: '書籍簡介' },
            { menu: '底層邏輯的定義' },
            { menu: '啟發' },
            { menu: '挑戰與反思' },
            { menu: '結語' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        >
          <template #brief>
            <p>
              這本書的作者，將我們的思維結構拆解成一個個簡單且可操作的層次，幫助讀者深入理解自己的思維過程，以及如何更有邏輯地面對生活中的種種挑戰。
            </p>
          </template>
        </Brief>
        <Content>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'書籍簡介'"
            />
            <p>
              《底層邏輯：如何解構世界的複雜性》（The Principles of Underlying Logic: How to Decode the Complexity of the World）是由著名思想家與決策學家劉潤所著。書中深入探討了「底層邏輯」這一概念，並提供了一套可操作的思維框架，幫助讀者理解如何從最基本的原則出發，解決日常生活和工作中的各種問題。
              <br>
              <br>
              書中的底層邏輯並非僅指單一的問題解決方法，而是一套結構化的思維模式，可以應用於任何領域，從個人選擇到企業策略，再到社會現象的分析。這本書既是對個人思維的深刻挑戰，也是對複雜世界簡化的嘗試，讓人重新思考如何面對不確定的未來。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'底層邏輯的定義'"
            />
            <p>
              底層邏輯是書中的核心概念，作者將其定義為一種追溯至最根本、最基本的規律和原則的思維方式。它要求我們在處理問題時，將注意力從表面現象轉向深層結構，洞察事物背後的共通邏輯，從而做出更加明智的決策。以下是書中介紹的一些重要原則和思維方式：
            </p>
            <ListNum :items="list1" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'啟發'"
            />
            <p>
              在閱讀這本書的過程中，我最大的啟發來自於底層邏輯的普遍性與應用性。無論是工作還是生活，我們每天面對的問題都往往是復雜且多變的。傳統的單一解決方案往往無法應對這些問題，但如果能夠從底層邏輯出發，運用這些普遍原則進行推理，就能夠揭示事物的本質，找到更有效的解決方案。
              <br>
              <br>
              例如，當面對職場中的困難時，我不再僅僅關注眼前的問題，而是會考慮到這些挑戰背後的系統性原因。這樣一來，解決方案不僅限於應對當前的挑戰，而是能夠在長期內持續產生積極的影響。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'挑戰與反思'"
            />
            <p>
              儘管底層邏輯提供了極為有價值的思維工具，但在實際應用中依然面臨一些挑戰。首先，習慣性的思維方式需要時間來改變，尤其是在面對突發情況或情緒激動時，我們往往會陷入短期決策的陷阱。其次，如何將理論中的底層邏輯應用於日常生活中，仍需要持續的練習和反思。
              <br>
              <br>
              最終，這本書讓我認識到，底層邏輯並非一成不變的思維工具，而是一種不斷進化的思維過程。隨著經驗的積累，我們可以不斷優化這些原則，並根據具體情境進行調整。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'結語'"
            />
            <p>
              總的來說，《底層邏輯》這本書為我提供了深刻的思考框架，讓我學會如何站在更高的視角來解讀世界的複雜性。無論是職場中的決策，還是生活中的選擇，底層邏輯都能幫助我做出更明智、更長遠的決定。
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
          title: "逆向思維（Inversion）",
          description: "逆向思維是一種經典的底層邏輯策略，強調從反向角度來看問題。換句話說，當我們面對一個問題時，不僅要思考「如何解決」，還要思考「如果要讓問題變得更糟，會怎麼做？」這樣的反向思考能夠幫助我們識別問題的根源，並找到被忽視的盲點。<br>舉例來說，若我們正在尋求提高工作效率的方式，反向思維則讓我們考慮「如何讓效率降低？」從這些想法中，我們便能夠意識到可能會影響效率的負面因素，進而更有針對性地提出解決方案。",
        },
        {
          title: "普遍原則（Universal Principles）",
          description: "在底層邏輯中，另一個關鍵概念是「普遍原則」。這些原則是可以跨越不同領域和情境的規律，不僅限於某個特定領域。書中提到的普遍原則包括時間的價值、複雜性的降低、機會與風險的平衡等。<br>「時間的價值」告訴我們，時間永遠是有限的資源，因此應該將更多的精力投入到那些能產生長期價值的活動中，而非短期的回報。",
        },
        {
          title: "大局觀（Big Picture Thinking）",
          description: "大局觀是一種將問題放大到整體、系統層面進行思考的方式。這要求我們不僅關注眼前的細節和短期結果，更要考慮長期影響和宏觀趨勢。這種思維模式能夠幫助我們更好地評估當前的決策，並預見可能的後果。<br>例如，在職業生涯規劃中，許多人往往專注於眼前的工作機會，忽略了整體職業生涯的發展方向。大局觀要求我們從長遠角度來看待每一個決策，並將短期的選擇與未來的目標緊密聯繫。",
        },
        {
          title: "系統思維（Systems Thinking）",
          description: "系統思維是底層邏輯中另一個重要的概念，強調將問題視為一個動態系統的一部分來理解和解決。系統中的各個元素是相互聯繫的，改變一個部分可能會對整個系統產生深遠的影響。",
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
          link: '/blog/post/3',
          title: "如何為你的 UI 設計選擇完美的配色方案？",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*ckOnmeIa3T-ASRMF1oGolg.png",
          date: "2024．09．17",
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