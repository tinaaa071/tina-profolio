<template>
  <div class="text-sm font-normal leading-relaxed bg-white cursor-default dark:bg-stone-900 text-stone-900 dark:text-white xs:text-base">
    <Layout :showProgress="true">
      <template #content>
        <div class="flex flex-col gap-6 mx-auto max-w-3xl md:pb-10">
          <Brief
          :post="{
          banner: 'https://cdn-images-1.medium.com/max/1600/1*FPPJYMZZ48qci9vCEW7n1A.png',
          credit: 'Design by Tina Chen',
          category: $t('blog.item4'),
          date: '2024．11．02',
          title: '16 個日系插圖精選網站推薦',
          desc: '日系插圖精選，讓你的創作更出色！',
        }"
        :showCredit="true"
        :showMenu="true"
        >
          <template #brief>
            <p>
              日系風格以其簡約、柔和與高辨識度的特色，深受設計師和創作者喜愛。今天將介紹 16 個精選的日系插圖素材網站，幫助你輕鬆找到理想素材。
            </p>
          </template>
        </Brief>
        <Content>
          <div class="flex flex-col gap-4">
            <H1 
            :title="'イラストAC'"
            :link="'https://www.ac-illust.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*f2nWfvtjoTXW2fyqOOwJrA.png"
              imgCredit="Credit: イラストAC"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list1[0], list1[1], list1[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list1[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'いらすとや'"
            :link="'https://www.irasutoya.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*BkWfINEpLsVZpGlVvJMdgQ.png"
              imgCredit="Credit: いらすとや"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list2[0], list2[1], list2[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list2[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Skribbl'"
            :link="'https://weareskribbl.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*T824gh-1U3hp5ixy.png"
              imgCredit="Credit: Skribbl"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list3[0], list3[1], list3[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list3[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Reshot'"
            :link="'https://www.reshot.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*1qsEZeBp6oVLtfpf"
              imgCredit="Credit: Reshot"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list4[0], list4[1], list4[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list4[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Open Doodle'"
            :link="'https://www.opendoodles.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*PQ5otlcE8VuIv_IR"
              imgCredit="Credit: Open Doodle"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list5[0], list5[1], list5[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list5[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Open Peeps'"
            :link="'https://www.openpeeps.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*0LfgPkCrGBJaChf2.jpg"
              imgCredit="Credit: Open Peeps"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list6[0], list6[1], list6[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list6[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'blush'"
            :link="'https://blush.design/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*PHUbIc6mHYCGGJJ8.jpg"
              imgCredit="Credit: blush"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list7[0], list7[1], list7[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list7[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'humaaans'"
            :link="'https://www.humaaans.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*AZqDZFBxuU5zdiZM"
              imgCredit="Credit: humaaans"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list8[0], list8[1], list8[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list8[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Control'"
            :link="'https://control.rocks/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*HuiU2JZvum07v3Z9.png"
              imgCredit="Credit: Control"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list9[0], list9[1], list9[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list9[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Cocomaterial'"
            :link="'https://cocomaterial.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*mT3ib89hGhMydpe0.jpg"
              imgCredit="Credit: Cocomaterial"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list10[0], list10[1], list10[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list10[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Ouch'"
            :link="'https://icons8.com/illustrations'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*djpYT02DmoWuSYbH.jpeg"
              imgCredit="Credit: Ouch"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list11[0], list11[1], list11[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list11[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'manypixels'"
            :link="'https://www.manypixels.co/gallery'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*a6ZiYNm9JI4cOU2A.jpeg"
              imgCredit="Credit: manypixels"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list12[0], list12[1], list12[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list12[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'freeillustrations'"
            :link="'https://freeillustrations.xyz/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*GepeZCS5NSjJKXSR.png"
              imgCredit="Credit: freeillustrations"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list13[0], list13[1], list13[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list13[3]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'illlustrations'"
            :link="'https://illlustrations.co/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*t5ppxYNTyAnbwWO8"
              imgCredit="Credit: illlustrations"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list14[0], list14[1], list14[2]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list14[3]]" />
            </div>
          </div>
          <Mention 
              :link="'/blog/post/4'" 
              :title="'16 個日系插圖精選網站推薦'" 
              :content="'快速提升設計質感！必收藏的 5 個 UI 配色資源'" 
              :image="'https://cdn-images-1.medium.com/max/1600/1*hx609LG91bVhVTfCBCf_bA.png'" 
            />
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
          description: "提供超過數萬件免費插圖，涵蓋多種風格與主題",
        },
        {
          description: "免費會員可下載高畫質圖片，商業用途無須額外授權",
        },
        {
          description: "使用者可以直接搜尋特定風格，如「手繪風」「可愛風」等",
        },
        {
          description: "部落格配圖、社群貼文設計、小型商業專案",
        }
      ],
      list2: [
        {
          description: "以簡單、可愛、略帶幽默的插圖著稱",
        },
        {
          description: "免費下載，商業用途也基本允許（需遵守網站條款）",
        },
        {
          description: "每日更新，覆蓋日常生活、職場、教育等多元場景",
        },
        {
          description: "教育課程、PPT製作、輕鬆活潑的品牌形象設計",
        }
      ],
      list3: [
        {
          description: "手繪風格插圖，帶有俏皮感和親和力",
        },
        {
          description: "可免費下載，用於商業用途需授權",
        },
        {
          description: "插圖具有高辨識度，能輕鬆提升品牌趣味性",
        },
        {
          description: "內容行銷、社群貼文、教育資源",
        }
      ],
      list4: [
        {
          description: "提供免費的高質量插圖和圖像，涵蓋多種主題",
        },
        {
          description: "適合用於數位媒體和設計專案",
        },
        {
          description: "支援個人和商業用途，素材更新頻繁",
        },
        {
          description: "網頁設計、PPT製作、品牌推廣",
        }
      ],
      list5: [
        {
          description: "免費的手繪風插圖庫，具有簡單但充滿趣味的風格",
        },
        {
          description: "可調整插圖配色，適用於多種數字平台",
        },
        {
          description: "開放授權，支援商業用途",
        },
        {
          description: "社群內容創作、教育資料、品牌設計",
        }
      ],
      list6: [
        {
          description: "專注於角色插圖，使用者可以自由組合臉部、身體和配件",
        },
        {
          description: "插圖手繪風，易於整合到各類設計中",
        },
        {
          description: "免費且商業用途友好",
        },
        {
          description: "人物介紹、社群圖像、品牌形象設計",
        }
      ],
      list7: [
        {
          description: "提供大量插圖組合工具，可即時編輯人物、背景、顏色",
        },
        {
          description: "與多位插畫師合作，涵蓋多種風格",
        },
        {
          description: "免費與付費選項，適合各種創意需求",
        },
        {
          description: "社群貼文、教育內容、品牌視覺識別",
        }
      ],
      list8: [
        {
          description: "高度可定制化的人物插圖，支援調整姿勢、衣著和顏色",
        },
        {
          description: "免費使用，特別適合描繪現代場景和人物故事",
        },
        {
          description: "插圖風格簡約，容易融入設計",
        },
        {
          description: "教學簡報、品牌推廣、應用程式設計",
        }
      ],
      list9: [
        {
          description: "插圖風格獨特，適合科技、現代化場景設計",
        },
        {
          description: "提供多種圖形和插圖元素，適用於專業設計",
        },
        {
          description: "免費和付費素材選擇多樣",
        },
        {
          description: "應用程式介面設計、科技品牌宣傳",
        }
      ],
      list10: [
        {
          description: "以柔和配色和清新風格為主，素材實用性高",
        },
        {
          description: "提供多種主題插圖，適合數位和實體設計",
        },
        {
          description: "免費下載，支援商業用途",
        },
        {
          description: "網站設計、行銷素材、手冊設計",
        }
      ],
      list11: [
        {
          description: "提供專業設計的免費插圖，涵蓋多種風格與主題",
        },
        {
          description: "插圖質量高，適合數位與實體設計",
        },
        {
          description: "免費用於商業項目，僅需簡單授權標註",
        },
        {
          description: "網頁和應用程式介面、產品推廣、品牌設計",
        }
      ],
      list12: [
        {
          description: "提供現代簡約風的插圖，可即時下載並使用",
        },
        {
          description: "適合品牌設計、數位媒體及印刷應用",
        },
        {
          description: "免費版與付費版素材均支援商業用途",
        },
        {
          description: "行銷專案、網站與應用設計、PPT插圖",
        }
      ],
      list13: [
        {
          description: "提供100%免費的矢量插圖，風格簡約而清新",
        },
        {
          description: "支援個人和商業用途，下載過程簡便",
        },
        {
          description: "插圖設計專業，適用於多種場景",
        },
        {
          description: "網頁設計、簡報、行銷活動",
        }
      ],
      list14: [
        {
          description: "提供免費的高質量插圖，專注於現代簡約風格",
        },
        {
          description: "插圖資源多樣，包括人物、物品、場景等多種元素",
        },
        {
          description: "允許商業用途，下載過程簡便，無需註冊即可使用",
        },
        {
          description: "網站設計、社群貼文、行銷資料、數位產品展示",
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