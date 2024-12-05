<template>
  <div class="bg-white sm:pb-10 dark:bg-stone-900 text-stone-900">
    <Navbar />
    <ProgressBar />
    <BackToTop class="z-20" />
    <div class="pt-24 pb-6 mx-auto min-h-screen sm:pt-28 md:pt-32">
      <Tabs
      :currentCategory="currentCategory"
      :categories="[
        $t('blog.item1') ,
        $t('blog.item2'),
        $t('blog.item3'),
        $t('blog.item4'),
        $t('blog.item5'),
      ]"
      @category-changed="filterByCategory"
      />

      <div class="px-6 sm:px-10 xl:px-28">
        <!-- Display "No data" message if no posts are available -->
        <div v-if="filteredPosts.length === 0" class="p-4 text-center">
          No data
        </div>

        <!-- Display PostList and Paginator only if there are posts -->
        <div v-else>
          <PostList :posts="paginatedPosts" :linkTo="/posts/" />

          <Paginator
            :totalItems="filteredPosts.length"
            :itemsPerPage="itemsPerPage"
            :currentPage="currentPage"
            @page-changed="handlePageChange"
          />
          <!-- <p>Current Page: {{ currentPage }}</p> -->
        </div>
      </div>
    </div>
  </div>
  <Footer />
</template>


<script>
export default {
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "介面設計原則：打造用戶友好體驗的基石",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*LSgS3r0VigNdsXHxAx9kqg.png",
          date: "2024．09．02",
        },
        {
          id: 2,
          title: "UI/UX 設計師如何培養美感？提升設計視野的實用指南",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*Qjgp1iIbw1IY2ww1AxfbPg.png",
          date: "2024．09．10",
        },
        {
          id: 3,
          title: "如何為你的 UI 設計選擇完美的配色方案？",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*ckOnmeIa3T-ASRMF1oGolg.png",
          date: "2024．09．17",
        },
        {
          id: 4,
          title: "5 個 UI 配色網站資源：提升設計質感的必備工具",
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*hx609LG91bVhVTfCBCf_bA.png",
          date: "2024．09．24",
        },
        {
          id: 5,
          title: "《原子習慣》 - 微小習慣如何帶來巨大改變",
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*kAq2lKvc-rZtuvjAFVOq_A.png",
          date: "2024．10．05",
        },
        {
          id: 6,
          title: "打造精美的 UI 設計：必備資源與工具",
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*Y8yyZ7mfWqM9DkBiEMyJQg.png",
          date: "2024．10．16",
        },
        {
          id: 7,
          title: "從零開始成為 UI/UX 設計師：自學路徑指南",
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*yJi3pvZRfffeHToNDhtSmQ.png",
          date: "2024．10．20",
        },
        {
          id: 8,
          title: "《Not Knowing》 - 擁抱未知，成就更廣闊的世界",
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*BoWK4m1ibJWviZh6U5rb4Q.png",
          date: "2024．10．28",
        },
        {
          id: 9,
          title: "14 個歐美插圖精選網站推薦",
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*e2YufV1qOiEC3uTYnhQl2Q.png",
          date: "2024．11．01",
        },
        {
          id: 10,
          title: "Lottie 動畫：打造更輕量、更高效的互動體驗",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/0*nGEzJ1WU_0eop9iQ.gif",
          date: "2024．11．02",
        },
        {
          id: 11,
          title: "LottieFiles：讓動畫設計與開發無縫接軌的革命性工具",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/0*YBzjF3NbL3ATmRch.png",
          date: "2024．11．03",
        },
        {
          id: 12,
          title: "16 個日系插圖精選網站推薦",
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*FPPJYMZZ48qci9vCEW7n1A.png",
          date: "2024．11．05",
        },
        {
          id: 13,
          title: "《底層邏輯》 - 看清這個世界的底牌",
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*hbzy5hAo2iubtbZ5u8gHNg.png",
          date: "2024．11．06",
        },
        {
          id: 14,
          title: "Bento Grid UI：靈感來自便當盒的介面設計風格",
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*XmqGmjWlFW0ZdY8xyTCGqA.png",
          date: "2024．11．08",
        },
        {
          id: 15,
          title: "《設計心理學》 - 理解人類行為與設計的橋樑",
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*l9LTo-VAunwN9UZeeoca4Q.png",
          date: "2024．11．12",
        },
        {
          id: 16,
          title: "UI/UX Designer 也要會寫程式嗎？",
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*OT0pTyXTOhQ2tuQzuqSwwg.png",
          date: "2024．11．13",
        },
        {
          id: 17,
          title: "12 款必備 Figma Plugins 推薦，提升設計效率的秘密武器",
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*FXqQSo8i5KrmhKGlImNUbA.png",
          date: "2024．11．15",
        },
        {
          id: 18,
          title: "身為 UI/UX 設計師開發的第一個 Figma Plugin - Shape Mask",
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*VUK2az0HJHzilzN0Rpgv0A.png",
          date: "2024．11．16",
        },
        // {
        //   id: 22,
        //   title: "Lottie 動畫：打造更輕量、更高效的互動體驗",
        //   category: this.$t('blog.item2'),
        //   image: "https://images.unsplash.com/photo-1628766416710-61d6f15f32b9?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        //   date: new Date().toLocaleDateString(),
        // },
      ],
      currentPage: 1,
      itemsPerPage: 12,
      currentCategory: this.$t('blog.item1'), // Set the default current category to "All"
    };
  },
  computed: {
    filteredPosts() {
      let posts = this.currentCategory === this.$t('blog.item1')
        ? this.posts
        : this.posts.filter((post) => post.category === this.currentCategory);

      // 排序 posts 依日期由新到舊
      return posts.sort((a, b) => new Date(b.date.replace(/．/g, '-')) - new Date(a.date.replace(/．/g, '-')));
    },
    paginatedPosts() {
      const start = (this.currentPage - 1) * this.itemsPerPage;
      const end = start + this.itemsPerPage;
      return this.filteredPosts.slice(start, end);
    },
  },
  methods: {
    handlePageChange(page) {
      this.currentPage = page;
      this.updateRoute(); // 每次頁碼變化時，更新路由查詢參數
    },
    updateRoute() {
      this.$router.push({
        path: this.$route.path,
        query: { ...this.$route.query, page: this.currentPage }, // 將 currentPage 放入查詢參數
      });
    },
    filterByCategory(category) {
      this.currentCategory = category;
      this.currentPage = 1; // 更改分類時重設頁碼為 1
      this.updateRoute(); // 更新路由
    },
  },
  watch: {
    '$route.query.page': {
      immediate: true,
      handler(newPage) {
        this.currentPage = newPage ? parseInt(newPage) : 1; // 如果查詢參數有 page，則使用該值，否則默認為 1
      },
    },
    '$route.query.category': {
      immediate: true,
      handler(newCategory) {
        if (newCategory) {
          this.currentCategory = newCategory;
        } else {
          this.currentCategory = this.$t('blog.item1');
        }
      },
    },
  },
};
</script>
