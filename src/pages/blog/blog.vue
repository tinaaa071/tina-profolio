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
    },
    filterByCategory(category) {
      this.currentCategory = category;
      this.currentPage = 1; // Reset to the first page when changing category
    },
  },
  watch: {
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
