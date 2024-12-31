<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*BoWK4m1ibJWviZh6U5rb4Q.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item5'),
          date: '2024．10．28',
          title: '《Not Knowing》 - 擁抱未知，成就更廣闊的世界',
          desc: '未知並非恐懼，而是探索與成長的起點',
          brief: '《Not Knowing: The Art of Turning Uncertainty into Possibility》這本書的兩位作者 Steven DSouza 和 Diana Renner 深刻剖析了「不確定性」這一看似負面的狀態，並提出了一種反直覺的觀點：接受並擁抱未知，不僅是面對現代複雜世界的關鍵能力，更是個人成長與創造力的催化劑。',
          menu: [
            { menu: '我們為什麼害怕不確定性？' },
            { menu: '不確定性是一種智慧的源泉' },
            { menu: '從「解答者」到「提問者」的轉變' },
            { menu: '混沌中的創造力' },
            { menu: '接受不確定性的實踐方法' },
            { menu: '從恐懼未知到欣賞未知' },
            { menu: '結語：未知是可能性的起點' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        @navigate="scrollToSection" 
        />
        <Content>
          <div class="flex flex-col gap-4" id="section1">
            <H1 
            :title="'我們為什麼害怕不確定性？'"
            />
            <p>
              我們都渴望對世界保持掌控。從選擇職業、計劃未來，到處理日常挑戰，我們習慣性地尋求答案，追求確定性。然而，這種對控制的渴望，是否也限制了我們的成長與創造力？
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'不確定性是一種智慧的源泉'"
            />
            <p>
              我們被教育要追求確定性的答案，認為知識的多寡代表了智慧的高度。但這本書開篇便顛覆了這一觀念：
            </p>
            <Callout>
              <H3
              :title="'「智慧不僅在於知道答案，更在於知道我們不知道什麼。」'"
              class="italic font-normal text-center"
              />
            </Callout>
            <p>
              作者用多個生動案例說明，那些願意坦承「我不知道」的人，往往比自以為是的「解答者」更能啟發他人。他們不僅激發了團隊的集體智慧，還為新的可能性鋪平了道路。
              <br>
              <br>
              書中提到一位創新型企業家，他面對市場的激烈競爭時，選擇擁抱未知，與團隊共同探索多種方案，最終找到了一條獨特的發展路徑。這提醒我們，未知並非失敗的象徵，而是創新的起點。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'從「解答者」到「提問者」的轉變'"
            />
            <p>
              人類對不確定性的焦慮，往往驅使我們過早尋求答案。但作者強調，當我們過於專注於快速解決問題時，可能會忽視更深層的挑戰和潛在的機會。
            </p>
            <Callout>
              <H3
              :title="'「偉大的領導者不是那些提供所有答案的人，而是那些敢於提出深刻問題的人。」'"
              class="italic font-normal text-center"
              />
            </Callout>
            <p>
              作者提出了一個實用的框架：
            </p>
            <ListDisc :items="list1" />
            <p>
              這種「提問者的心態」不僅適用於職場，也能幫助我們在個人生活中更靈活地應對挑戰。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'混沌中的創造力'"
            />
            <p>
              我們常常害怕混亂，認為秩序才是進步的基礎。但《Not Knowing》指出，混亂其實是創造力的最佳土壤。書中舉了一個有趣的例子：一些知名的藝術家與科學家，都是在經歷失敗與不確定的階段中，找到突破性的靈感。
            </p>
            <Callout>
              <H3
              :title="'「創造力的火花，往往來自於我們無法控制的瞬間。」'"
              class="italic font-normal text-center"
              />
            </Callout>
            <p>
              這讓我聯想到自己的一次經驗：在一個重要項目中，我和團隊無法確定最佳解決方案，我們嘗試了不同的想法，甚至經歷了幾次失敗。但正是在這些「迷失」的過程中，我們意外地發現了一個更創新的方向，結果超出了所有人的預期。
            </p>
            <Callout>
              <H3
              :title="'混亂並不可怕，真正的創造力需要我們學會與混亂共存。'"
              class="italic font-normal text-center"
              />
            </Callout>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'接受不確定性的實踐方法'"
            />
            <p>
              除了哲學層面的啟發，這本書還提供了一些實際的方法，幫助我們在日常生活中更好地應對不確定性：
            </p>
            <ListDisc :items="list2" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section6">
            <H1 
            :title="'從恐懼未知到欣賞未知'"
            />
            <p>
              過去，我常常因為無法預測結果而感到焦慮，總想掌控一切。然而，作者的觀點幫助我看見了一個全新的視角：未知並非需要解決的問題，而是一個值得探索的機會。
              <br>
              <br>
              在工作上，我嘗試減少對立即解決問題的執著，進行更多開放式的討論，這種方式不僅提升了我們的創造力，也減少了壓力感。
              <br>
              <br>
              在生活中，我也練習接納更多的不確定性。面對未來，我學會了對自己說：「不知道現在答案也沒關係。」
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section7">
            <H1 
            :title="'結語：未知是可能性的起點'"
            />
            <p>
              《Not Knowing: The Art of Turning Uncertainty into Possibility》不僅是一本關於應對不確定性的指南，更是一種新思維的啟發。它挑戰我們重新審視「不確定性」的意義，並提醒我們，成長往往來自於我們最害怕的領域。
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
          title: "慢下來，反思問題的本質",
          description: "這個問題是否真的需要立即解答？還是有探索的空間？",
        },
        {
          title: "提問，而非斷言",
          description: "例如，與其說「這是行不通的」，不如問「有什麼方法能讓這行得通？」",
        },
        {
          title: "接受暫時的模糊性",
          description: "模糊並不可怕，因為它可能隱藏著更多的潛在可能性。",
        }
      ],
      list2: [
        {
          title: "培養好奇心",
          description: "嘗試問自己：「我還能學到什麼？」或者「有什麼是我還未考慮的？」這種開放式的思考方式，能幫助我們發現更多可能性。",
        },
        {
          title: "擁抱錯誤與失敗",
          description: "書中強調，失敗並非終點，而是學習的起點。記住，錯誤讓我們更接近真相。",
        },
        {
          title: "練習放下控制",
          description: "每天給自己一段時間，允許未知存在。例如，不要立即為某個問題找答案，試著觀察事情的自然發展。",
        }
      ],
      list3: [
        {
          title: "開始很小，專注當下",
          description: "不管是什麼習慣，最重要的是開始，而不是完美。",
        },
        {
          title: "積少成多，重視過程",
          description: "只要持續做，時間會成為你的盟友。",
        },
        {
          title: "改變環境，支持行為",
          description: "打造一個促進好習慣的環境，比僅靠意志力更有效。",
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