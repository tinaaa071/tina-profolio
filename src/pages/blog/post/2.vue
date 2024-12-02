<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*Qjgp1iIbw1IY2ww1AxfbPg.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item2'),
          date: '2024-09-10',
          title: 'UI/UX 設計師如何培養美感？提升設計視野的實用指南',
          desc: '從平凡到驚豔，UI/UX 設計師的美感修煉之路！',
          menu: [
            { menu: '觀察日常生活中的設計' },
            { menu: '學習設計基礎理論' },
            { menu: '多接觸不同風格與文化' },
            { menu: '養成設計輸出習慣' },
            { menu: '提升與非設計師的溝通能力' }
          ]
        }"
        :showCredit="true"
        :showMenu="true"
        >
          <template #brief>
            <p>
              美感，是 UI/UX 設計師不可或缺的能力之一。
              <br>
              雖然美感的養成似乎是天生的，但實際上透過後天的學習和練習，同樣可以大幅提升設計敏感度，讓作品更具吸引力與功能性。
            </p>
          </template>
        </Brief>
        <Content>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'1. 觀察日常生活中的設計'"
            />
            <p>
              美感並不僅限於螢幕上的界面，生活中到處都有值得學習的設計。
            </p>
            <ListDisc :items="list1" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*gEhekT-JtKQ1Vo5e.jpg"
              imgCredit="Credit: 松菸"
            />
          </div>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'2. 學習設計基礎理論'"
            />
            <p>
              設計美感不僅來自直覺，更需要穩固的基礎理論。
            </p>
            <ListDisc :items="list2" />
          </div>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'3. 多接觸不同風格與文化'"
            />
            <p>
              設計靈感不該局限於單一文化或風格。多元的視角能讓你的設計更具包容性和深度。
            </p>
            <ListDisc :items="list3" />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*J5durJaN_z2dhX6M"
            />
          </div>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'4. 養成設計輸出習慣'"
            />
            <p>
              培養美感的同時，也需要持續實踐。
            </p>
            <ListDisc :items="list4" />
          </div>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'5. 提升與非設計師的溝通能力'"
            />
            <p>
              美感的養成不僅來自個人努力，也需要與他人的互動。
            </p>
            <ListDisc :items="list5" />
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'結語：設計美感是一種持續進化的能力'"
            />
            <p>
              UI/UX 設計師的美感養成需要時間與努力，但只要不斷觀察、學習、實踐，設計敏銳度將會日益提升。記住，美感並非追求表面的「漂亮」，而是透過設計達成功能性與情感連結的平衡。
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
          title: "觀察實體世界",
          description: "留意建築、海報、包裝設計，思考它們的配色、排版和材質如何產生和諧感。",
        },
        {
          title: "數位界面",
          description: "分析常用的應用程式或網站，嘗試找出令你覺得吸引的設計元素，並記錄下來。",
        }
      ],
      list2: [
        {
          title: "色彩學",
          description: "學習色彩搭配的基礎原理，例如對比色、互補色、色調心理學。",
        },
        {
          title: "排版設計",
          description: "瞭解字體分類、字距與行距的處理，讓畫面更具一致性。",
        },
        {
          title: "構圖與比例",
          description: "掌握黃金比例、三分法，為畫面建立平衡感。",
        }
      ],
      list3: [
        {
          title: "研究設計史",
          description: "探索不同時期的設計風格，如包豪斯、極簡主義、後現代主義等。",
        },
        {
          title: "體驗異文化設計",
          description: "了解日本禪風的極簡、北歐設計的功能性與美感等文化特色。",
        }
      ],
      list4: [
        {
          title: "臨摹設計作品",
          description: "選擇你喜歡的作品，重新創建一遍，並試著加入自己的創意。",
        },
        {
          title: "設計挑戰",
          description: "參與 100 天設計挑戰，將每日練習變成習慣。",
        },
        {
          title: "社群回饋",
          description: "將作品發佈到設計社群，聽取他人的建議與回饋。",
        }
      ],
      list5: [
        {
          title: "設計交付",
          description: "與工程師討論設計如何落地，從技術限制中找到創意解決方案。",
        },
        {
          title: "體驗測試",
          description: "與用戶測試，了解視覺設計如何影響用戶體驗。",
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