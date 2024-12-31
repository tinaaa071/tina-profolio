<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*l9LTo-VAunwN9UZeeoca4Q.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item5'),
          date: '2024．11．05',
          title: '《設計心理學》 - 理解人類行為與設計的橋樑',
          desc: '人性與設計的交匯點，創造更好的世界',
          brief: '在現今充滿設計的世界裡，無論是產品、服務還是應用程式，設計都與我們的生活息息相關。如何設計出符合人類需求、習慣與心理的產品？',
          menu: [
            { menu: '書籍簡介' },
            { menu: '核心觀點' },
            { menu: 'Norman 的設計原則' },
            { menu: '分析與反思' },
            { menu: '結語' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        @navigate="scrollToSection" 
        />
        <Content>
          <p>
            這本由唐納德·諾曼（Donald A. Norman）所著的《設計心理學》（The Design of Everyday Things）為我們提供了豐富的洞見。這不僅僅是一本關於設計的書，它深入探討了人類行為如何影響我們對事物的使用，以及設計師如何理解這些行為來創造更好的用戶體驗。
          </p>
          <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*Pp7QWzR9tqmmr0yS"
            />
          <div class="flex flex-col gap-4" id="section1">
            <H1 
            :title="'書籍簡介'"
            />
            <p>
              《設計心理學》首次出版於1988年，是一本探討日常物品設計的經典之作。唐納德·諾曼是一位認知科學家和設計專家，他以深入淺出的語言，將複雜的心理學與設計理論結合起來，解釋了為何有些產品的使用體驗是順暢的，而有些則讓人感到困惑或沮喪。書中不僅探討了設計的理論，還通過具體的案例，揭示了設計和心理學之間的緊密關聯。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'核心觀點'"
            />
            <ListNum :items="list1" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'Norman 的設計原則'"
            />
            <p>
              在《設計心理學》中，唐納德·諾曼提出了一些基本的設計原則，幫助設計師創造出更符合用戶需求的產品。以下是一些核心原則：
            </p>
            <ListNum :items="list2" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'分析與反思'"
            />
            <p>
              在閱讀《設計心理學》時，我不禁反思了自己日常使用的各種產品。無論是手機、電腦還是家中的小家電，它們背後都隱藏著設計師對人類心理的理解和設計的巧思。以手機為例，許多設計師會將最常用的功能放在最容易觸及的位置，這樣用戶在操作時能夠避免不必要的動作。
              <br>
              <br>
              然而，書中所提的「錯誤設計」也讓我意識到，許多現代產品仍然存在設計缺陷。尤其是當我們在快速移動、工作壓力大或情境複雜時，設計的不友好可能導致用戶體驗的失敗。像是某些應用程式過於複雜的界面設計，往往讓用戶感到迷失，這正是《設計心理學》所警告的設計錯誤。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'結語'"
            />
            <p>
              總的來說，《設計心理學》不僅是一本設計書，它是一部探討人類行為與設計哲學的作品。無論你是設計師、產品經理還是對設計有興趣的讀者，這本書都能帶給你深刻的洞察和啟發。作為讀者，我從中學到的不僅僅是設計的技巧，還是如何理解和尊重使用者的需求，以及如何將這些需求與設計結合，創造出更符合人類心理的產品。
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
          title: "可用性與直覺",
          description: "諾曼在書中強調，優秀的設計應該是直觀的。使用者不需要閱讀長篇的使用手冊，而是能夠通過產品的外觀和結構，自然而然地理解如何使用它。這一觀點對於現代的數位產品設計尤其重要，因為人們越來越希望能夠快速、無縫地操作技術。",
        },
        {
          title: "錯誤的設計是設計的失敗",
          description: "書中還談到，許多設計問題的根源在於設計師未能考慮到用戶的錯誤行為。人類是會犯錯的，設計師應該預測並減少使用過程中的錯誤，讓產品能夠引導用戶正確操作。",
        },
        {
          title: "人類心理與設計的交集",
          description: "書中的一個重要觀點是，設計不僅僅是關於美學，它還涉及到人類的認知心理學。產品的功能和外觀要與人的感知、記憶和理解方式匹配。設計師需要了解人類如何感知世界，並運用這些知識來創造更符合人類需求的產品。",
        }
      ],
      list2: [
        {
          title: "可見性（Visibility）",
          description: "諾曼強調，產品的功能應該是顯而易見的。良好的設計會讓用戶能夠一眼看出哪些部件可以操作，這有助於減少學習成本，並避免使用錯誤。例如，門把手的設計要清楚地顯示出如何開門，而不需要用戶猜測或反覆試驗。",
        },
        {
          title: "反饋（Feedback）",
          description: "設計需要提供即時的反饋，告訴用戶他們的操作是否成功。例如，按下按鈕後，應該立即給予視覺或聲音反饋，讓用戶知道他們的行為已被系統接收並執行。缺乏反饋的設計會讓用戶感到迷茫或困惑，並且增加使用錯誤的機會。",
        },
        {
          title: "限制（Constraints）",
          description: "諾曼指出，設計應該利用物理、邏輯或語義上的限制來防止用戶犯錯。這些限制可以指引用戶在正確的範疇內進行操作。例如，USB 接頭設計上有所謂的「形狀限制」，使得用戶無法錯誤地插入，這樣的限制能有效避免操作錯誤。",
        },
        {
          title: "映射（Mapping）",
          description: "映射指的是操作界面與其效果之間的直觀關係。例如，當你調整洗衣機上的旋鈕時，旋鈕的轉動應該與洗衣機的功能或操作邏輯自然對應。良好的映射能使操作變得簡單直觀，並提升用戶體驗。",
        },
        {
          title: "一致性（Consistency）",
          description: "一致性原則要求設計保持內部的一致性。也就是說，設計中的各個部分應該遵循相同的規則和模式，讓用戶可以輕鬆理解和預測操作。例如，所有按鈕應該在顏色、形狀或位置上保持一致，這樣用戶可以在不同界面中快速適應。",
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