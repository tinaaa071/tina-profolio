<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*ckOnmeIa3T-ASRMF1oGolg.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item2'),
          date: '2024．09．17',
          title: '如何為你的 UI 設計選擇完美的配色方案？',
          desc: '選對配色，讓你的設計從視覺中脫穎而出！',
          brief: '在 UI 設計中，配色方案是影響使用者體驗的關鍵因素之一。<br>一個好的配色方案不僅能提升美觀性，還能幫助使用者更直觀地理解產品資訊。',
          menu: [
            { menu: '為什麼 UI 配色如此重要？' },
            { menu: 'UI 配色的 4 大基本原則' },
            { menu: '配色實踐：從工具到實例' },
            { menu: '實例分享' },
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
            :title="'為什麼 UI 配色如此重要？'"
            />
            <p>
              配色直接影響到：
            </p>
            <ListDisc :items="list1" />
            <p>
              如果配色選得不好，不僅會影響產品的美感，甚至可能讓使用者感到困惑或視覺疲勞。
            </p>
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*6OSGO4XZ9H7qtudF.png"
              imgCredit="Credit: airbnb"
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section2">
            <H1 
            :title="'UI 配色的 4 大基本原則'"
            />
            <ListNum 
            :items="list2"
            customClass="space-y-4"
            >
              <template #slot-0>
                <ListDisc :items="list3" />
                <CreditImg 
                  imgSrc="https://cdn-images-1.medium.com/max/1600/0*Nmlu2g59MzwTVMZW.png"
                  class="mt-4"
                />
              </template>
              <template #slot-1>
                <ListDisc :items="list4" />
                <CreditImg 
                  imgSrc="https://cdn-images-1.medium.com/max/1600/0*3Z6Q6Zb6OK6EFD6q.png"
                  imgCredit="Credit: marvelapp"
                  class="mt-4"
                />
              </template>
              <template #slot-2>
                <ListDisc :items="list5" />
                <CreditImg 
                  imgSrc="https://cdn-images-1.medium.com/max/1600/0*7hXSv1-_lo-68dVO.png"
                  imgCredit="Credit: Canva"
                  class="mt-4"
                />
              </template>
              <template #slot-3>
                <CreditImg 
                  imgSrc="https://cdn-images-1.medium.com/max/1600/0*FtW95kX1puUkAb3h.png"
                  imgCredit="Credit: WebAIM Contrast Checker"
                  class="mt-4"
                />
              </template>
            </ListNum>
          </div>
          <div class="flex flex-col gap-4" id="section3">
            <H1 
            :title="'配色實踐：從工具到實例'"
            />
            <p>
              實用的配色工具
            </p>
            <ListNum :items="list6" />
            <Mention 
              :link="'/blog/post/4'" 
              :title="'5 個 UI 配色網站資源：提升設計質感的必備工具'" 
              :content="'快速提升設計質感！必收藏的 5 個 UI 配色資源'" 
              :image="'https://cdn-images-1.medium.com/max/1600/1*hx609LG91bVhVTfCBCf_bA.png'" 
            />
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section4">
            <H1 
            :title="'實例分享'"
            customClass="space-y-4"
            />
            <ListNum 
            :items="list7"
            >
            <template #slot-0>
              <ListDisc :items="list8" />
              <CreditImg 
                imgSrc="https://imockups.com/storage/product/3873/KAnjM5jdOQAHLJNbYjoA.png"
                class="mt-4"
              />
            </template>
            <template #slot-1>
              <ListDisc :items="list8" />
              <CreditImg 
                imgSrc="https://cdn-images-1.medium.com/max/1600/0*vbUbrqBaHu1YYsg4.jpeg"
                class="mt-4"
              />
            </template>
          </ListNum>
          </div>
          <Dot />
          <div class="flex flex-col gap-4" id="section5">
            <H1 
            :title="'結語'"
            />
            <p>
              選擇 UI 配色方案不僅是藝術，更是一門科學。好的配色能讓設計脫穎而出，提升產品的易用性與吸引力。無論是遵循色彩心理學，還是善用工具與對比度，最重要的是確保配色與使用者需求和品牌一致。
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
          title: "使用者情感",
          description: "不同的顏色能引發不同的情緒，例如藍色帶來信任感，而紅色則代表警告或緊急狀態。",
        },
        {
          title: "資訊層級",
          description: "通過對比與色彩強調，讓使用者快速抓住重點資訊。",
        },
        {
          title: "品牌一致性",
          description: "顏色是品牌識別的重要元素，確保設計符合品牌視覺。",
        }
      ],
      list2: [
        {
          title: "了解色彩心理學",
          description: "不同顏色有各自的象徵意義。例如：",
        },
        {
          title: "善用色彩對比",
          description: "對比度可以幫助強調內容。例如：",
        },
        {
          title: "採用色彩和諧原則",
          description: "選用和諧的配色方案，避免顏色過多或過於衝突。常用的配色方案有：",
        },
        {
          title: "考慮無障礙設計",
          description: "確保配色對於視力受損的使用者也是友善的。可以使用工具檢測色彩的對比度，如 WebAIM Contrast Checker。",
        }
      ],
      list3: [
        {
          title: "藍色",
          description: "冷靜、專業，適合科技產品或金融服務。",
        },
        {
          title: "綠色",
          description: "健康、自然，常見於環保或健康相關應用。",
        },
        {
          title: "黃色",
          description: "活力與注意，適合需要高注意力的設計元素。",
        }
      ],
      list4: [
        {
          description: "選擇你喜歡的作品，重新創建一遍，並試著加入自己的創意。",
        },
        {
          description: "在按鈕或警告訊息中，選用高對比色，讓使用者能快速識別。",
        }
      ],
      list5: [
        {
          title: "單色系",
          description: "使用同一色調的不同亮度和飽和度。",
        },
        {
          title: "類似色系",
          description: "選用色環上相鄰的顏色，營造柔和感。",
        },
        {
          title: "互補色系",
          description: "選用色環上相對的顏色，產生強烈的對比效果。",
        }
      ],
      list6: [
        {
          title: "Coolors",
          description: "生成和調整配色方案。",
        },
        {
          title: "Adobe Color",
          description: "探索和設計專業配色方案。",
        },
        {
          title: "Material Design Color Tool",
          description: "符合 Material Design 指南的配色工具。",
        }
      ],
      list7: [
        {
          title: "案例一：金融應用"
        },
        {
          title: "案例二：健身應用"
        }
      ],
      list8: [
        {
          title: "主色",
          description: "深藍色（象徵信任）",
        },
        {
          title: "輔助色",
          description: "灰色（穩定）",
        },
        {
          title: "強調色",
          description: "橙色（吸引注意力，用於按鈕或 CTA）",
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