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
          desc: '微小習慣，改寫人生，每天 1% 的進步創造巨大改變！',
          menu: [
            { menu: '核心觀點解析' },
            { menu: '個人反思與應用' },
            { menu: '挑戰與學習' },
            { menu: '心法總結' },
            { menu: '結語：讓行動帶來改變' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        >
          <template #brief>
            <p>
              《Not Knowing: The Art of Turning Uncertainty into Possibility》這本書的兩位作者 Steven D'Souza 和 Diana Renner 深刻剖析了「不確定性」這一看似負面的狀態，並提出了一種反直覺的觀點：接受並擁抱未知，不僅是面對現代複雜世界的關鍵能力，更是個人成長與創造力的催化劑。
            </p>
          </template>
        </Brief>
        <Content>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'核心觀點解析'"
            />
            <H2 
            :title="'🔹&nbsp;&nbsp;1% 的進步法則'"
            />
            <p>
              James Clear 用一個簡單的數學模型讓我醍醐灌頂：如果你每天進步 1%，一年後的成效會是原來的 37 倍。但相反的，如果每天退步 1%，一年後的結果幾乎會趨近於零。這表明，習慣的力量來自於日積月累的小行動，而非偶爾的大動作。
            </p>
            <br>
            <H2 
            :title="'🔹&nbsp;&nbsp;習慣的四個法則'"
            />
            <p>
              為了幫助我們更容易建立好習慣，作者提出了一套「習慣循環」的框架，包含四個法則：
            </p>
            <ListDisc :items="list1" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'個人反思與應用'"
            />
            <p>
              在閱讀這本書之後，我開始用它的框架實驗一些小習慣，並觀察它們如何影響我的生活。
            </p>
            <div>
              <H3 
              :title="'⏰&nbsp;&nbsp;建立早起的習慣'"
              class="mb-2"
              />
              <p>
                過去，我一直覺得早起很困難，常常按下鬧鐘後又倒頭大睡。依照「降低門檻」的法則，我做了幾個小改變：
              </p>
            </div>
            <ListDisc :items="list2" />
            <CreditImg 
              imgSrc="https://images.unsplash.com/photo-1518863339959-768cb564a095?q=80&w=2746&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
              imgCredit="Credit: Unsplash"
            />
            <p>
              這些小改變讓我逐漸適應早起，並且發現早晨安靜的時光能大幅提升一天的專注力和效率。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'挑戰與學習'"
            />
            <p>
              儘管我在實踐中取得了一些進展，但也遇到不少挑戰。例如，有時候進步緩慢會讓人感到挫折，特別是在結果不明顯的初期階段。作者的觀點幫助了我：與其過於專注於目標，倒不如著眼於系統和過程。
              <br>
              他提到，「你無法達到超越系統的目標。」這句話深深觸動了我。我開始檢視自己的生活系統，並持續優化它們。例如，我不再期待短期內能完成巨大的工作，而是設計了一個每天進行 30 分鐘深度工作的流程，這讓我在長期內更容易保持穩定的輸出。
            </p>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'心法總結'"
            />
            <ListNum :items="list3" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'結語：讓行動帶來改變'"
            />
            <p>
              人生就像一艘航行中的船，習慣是那微小的舵。改變舵的方向，即使只是一點點，最終都能讓你抵達一個全然不同的目的地。《原子習慣》讓我明白了這個道理，也希望它能幫助你找到改變的契機。
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
          title: "明確化",
          description: "讓好習慣顯而易見。例如，我想養成每天喝水的習慣，就會在桌上擺一個裝滿水的透明杯子，讓它成為一個視覺提示。",
        },
        {
          title: "吸引力",
          description: "讓好習慣更有吸引力。我把運動與聽音樂結合，只有在運動時才播放自己喜歡的歌單，這讓我對運動更加期待。",
        },
        {
          title: "容易性",
          description: "降低習慣的門檻。如果想開始閱讀，我會把書放在隨手可拿的地方，並設定每天只讀一頁的低標準，這樣起步變得輕而易舉。",
        },
        {
          title: "滿足感",
          description: "讓習慣的結果令人愉悅。我會為每完成一次小目標打勾，讓自己從視覺上感受到進步帶來的成就感。",
        }
      ],
      list2: [
        {
          title: "前一天準備好一切",
          description: "晚上睡前整理好工作用品，並將重要的計劃寫在筆記本上，讓早晨醒來時有明確的行動目標。",
        },
        {
          title: "設置環境提示",
          description: "把鬧鐘放在離床較遠的地方，讓自己必須起身才能關掉鬧鐘。",
        },
        {
          title: "製造獎勵",
          description: "為了讓早起更有吸引力，我允許自己一邊喝咖啡，一邊看一部小短片作為晨間儀式。",
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