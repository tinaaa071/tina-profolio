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
          brief: '日系風格以其簡約、柔和與高辨識度的特色，深受設計師和創作者喜愛。今天將介紹 16 個精選的日系插圖素材網站，幫助你輕鬆找到理想素材。'
        }"
        :showCredit="true"
        :showMenu="true"
        />
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
            :title="'イラストセンター'"
            :link="'https://illustcenter.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*l0sIWQ5T6UgusASQ0MtSmQ.png"
              imgCredit="Credit: イラストセンター"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list3[0], list3[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list3[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'時短だ'"
            :link="'https://jitanda.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*2hGpfadlQVrtqh8P8NvKag.png"
              imgCredit="Credit: 時短だ"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list4[0], list4[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list4[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'rakugakiicon'"
            :link="'https://rakugakiicon.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*XmKCmsge3LwoFh2tH2fBng.png"
              imgCredit="Credit: rakugakiicon"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list5[0], list5[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list5[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'STAMPO'"
            :link="'https://stampo.fun/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*Oe0y4-iUzSoOA7TD.jpg"
              imgCredit="Credit: STAMPO"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list6[0], list6[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list6[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'ソコス'"
            :link="'https://soco-st.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*3QLUh4WrdWw-xNJp.png"
              imgCredit="Credit: ソコス"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list7[0], list7[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list7[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Shigureni free illust'"
            :link="'https://www.shigureni.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*BSpqK7ZV9B8uJljP.png"
              imgCredit="Credit: Shigureni free illust"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list8[0], list8[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list8[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'ベクターシェルフ (Vector Shelf)'"
            :link="'https://vectorshelf.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*wX7C_eXeXjXJAaG3.jpg"
              imgCredit="Credit: ベクターシェルフ (Vector Shelf)"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list9[0], list9[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list9[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'ダ鳥獣戯画'"
            :link="'https://chojugiga.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*TCZpNPZBgqegE-up.png"
              imgCredit="Credit: ダ鳥獣戯画"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list10[0], list10[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list10[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Linustock'"
            :link="'https://www.linustock.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*S3wtlMZr1O_XvgKk.jpg"
              imgCredit="Credit: Linustock"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list11[0], list11[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list11[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'えんぴつ素材'"
            :link="'https://enpitsu-sozai.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*cs_53SjFGiplI9vy"
              imgCredit="Credit: えんぴつ素材"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list12[0], list12[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list12[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'Web-sozai'"
            :link="'https://web-sozai.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/1*7bzyuPNENydZq_eF5t-B_A.png"
              imgCredit="Credit: Web-sozai"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list13[0], list13[1]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list13[2]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'ICOOON MONO'"
            :link="'https://icooon-mono.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*3wzD2DWjlAsz_u9U"
              imgCredit="Credit: ICOOON MONO"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list14[0], list14[1], list14[2], list14[3]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list14[4]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'TOWN illust'"
            :link="'https://town-illust.com/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*iO3aFGU0ZbipkrHh.png"
              imgCredit="Credit: TOWN illust"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list15[0], list15[1], list15[2], list15[3]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list15[4]]" />
            </div>
          </div>
          <Dot />
          <div class="flex flex-col gap-4">
            <H1 
            :title="'DOTOWN'"
            :link="'https://dotown.maeda-design-room.net/'"
            />
            <CreditImg 
              imgSrc="https://cdn-images-1.medium.com/max/1600/0*x31dYLXqjteC2Q34"
              imgCredit="Credit: DOTOWN"
            />
            <div>
              <span>網站特色：</span>
              <ListDisc :items="[list16[0], list16[1], list16[2], list16[3]]" />
            </div>
            <div>
              <span>適合使用場景：</span>
              <ListDisc :items="[list16[4]]" />
            </div>
          </div>
          <Mention 
              :showNote="true"
              :link="'/blog/post/9'" 
              :title="'14 個歐美插圖精選網站推薦'" 
              :content="'精挑細選！設計師必備的 14 個歐美插圖網站推薦！'" 
              :image="'https://cdn-images-1.medium.com/max/1600/1*e2YufV1qOiEC3uTYnhQl2Q.png'" 
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
          description: "提供各種專業插圖素材，分為多種主題",
        },
        {
          description: "適用於商業用途，並提供範本與素材包",
        },
        {
          description: "行銷設計、專業報告、商業插圖",
        },
        {
          description: "內容行銷、社群貼文、教育資源",
        }
      ],
      list4: [
        {
          description: "提供多種免費插圖，設計簡約而富有趣味性",
        },
        {
          description: "主要以日常生活為題材，適合商業與個人用途",
        },
        {
          description: "網站設計、商業宣傳資料、社交媒體圖像",
        }
      ],
      list5: [
        {
          description: "提供可愛的手繪風格插圖，素材風格活潑、親和力強",
        },
        {
          description: "免費下載並允許商業用途",
        },
        {
          description: "社群平台封面設計、品牌插圖、輕鬆活潑的活動宣傳",
        }
      ],
      list6: [
        {
          description: "特色是手繪風格的插圖，質感細膩",
        },
        {
          description: "提供免費下載，素材多元，且分為多種類型",
        },
        {
          description: "插圖設計、教學材料、商品包裝設計",
        }
      ],
      list7: [
        {
          description: "擁有各式手繪風格插圖，並且免費提供",
        },
        {
          description: "允許用於商業用途，但需遵循使用規範",
        },
        {
          description: "學校資料、報告封面、產品設計",
        }
      ],
      list8: [
        {
          description: "提供免費且高質量的日系插圖，具有精緻的風格",
        },
        {
          description: "提供多樣的下載格式，方便設計師使用",
        },
        {
          description: "線上媒體、產品推廣、社交媒體圖像",
        }
      ],
      list9: [
        {
          description: "提供大量的向量插圖和圖形，主題涵蓋廣泛",
        },
        {
          description: "高解析度，適合設計師用於印刷或數位設計",
        },
        {
          description: "專業設計工作、印刷設計、廣告設計",
        }
      ],
      list10: [
        {
          description: "以插畫的經典日式藝術風格為主題",
        },
        {
          description: "插圖風格古雅，適合文化、教育用途",
        },
        {
          description: "文化推廣、教育資料、藝術展覽",
        }
      ],
      list11: [
        {
          description: "以插圖為主，結合簡約風格和現代設計",
        },
        {
          description: "支援高解析度下載，並提供商業用途素材",
        },
        {
          description: "商業設計、網站與應用程式設計",
        }
      ],
      list12: [
        {
          description: "以鉛筆風格插圖為特色，適合用於手繪感強烈的設計",
        },
        {
          description: "提供多樣化素材，適合各類專案需求",
        },
        {
          description: "手繪風格設計、手冊封面、社群設計",
        }
      ],
      list13: [
        {
          description: "提供大量免費插圖，風格簡約多樣",
        },
        {
          description: "支援商業用途，並設有多個分類方便搜尋",
        },
        {
          description: "網頁設計、品牌推廣、電子書封面",
        }
      ],
      list14: [
        {
          description: "提供大量的高質量免費插圖，專注於簡約和現代風格",
        },
        {
          description: "插圖種類豐富，包括圖標、背景、人物等各式素材",
        },
        {
          description: "支援多種格式下載，適用於數位設計、印刷以及網頁設計等用途",
        },
        {
          description: "可免費下載並用於商業用途，但需遵守網站的授權條款",
        },
        {
          description: "網站設計、應用程式介面設計、行銷資料、產品推廣素材",
        }
      ],
      list15: [
        {
          description: "提供以「城鎮生活」為主題的插圖，風格清新自然",
        },
        {
          description: "主題涵蓋日常生活、店鋪場景、交通工具等多元內容",
        },
        {
          description: "免費下載並允許商業用途，需依據使用條款標註來源",
        },
        {
          description: "插圖細膩而實用，適合描繪溫馨故事或展示社區氛圍的專案",
        },
        {
          description: "地方社區宣傳、教育教材、品牌故事視覺設計",
        }
      ],
      list16: [
        {
          description: "提供大量以點陣圖（像素藝術）為主的插圖素材",
        },
        {
          description: "風格復古又可愛，涵蓋角色、物件、場景等多種主題",
        },
        {
          description: "免費提供高質量下載，支援商業用途，但需標明出處並遵守網站使用條款",
        },
        {
          description: "素材精緻，特別適合需要懷舊或遊戲風格的設計專案",
        },
        {
          description: "遊戲設計、像素藝術相關專案、社群貼文、復古風品牌設計",
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