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
  computed: {
    posts() {
      return [
      {
          id: 1,
          title: this.$t('post1.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*LSgS3r0VigNdsXHxAx9kqg.png",
          date: "2024．08．02",
        },
        {
          id: 2,
          title: this.$t('post2.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*Qjgp1iIbw1IY2ww1AxfbPg.png",
          date: "2024．08．10",
        },
        {
          id: 3,
          title: this.$t('post3.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*ckOnmeIa3T-ASRMF1oGolg.png",
          date: "2024．08．17",
        },
        {
          id: 4,
          title: this.$t('post4.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*hx609LG91bVhVTfCBCf_bA.png",
          date: "2024．08．24",
        },
        {
          id: 5,
          title: this.$t('post5.core.title'),
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*kAq2lKvc-rZtuvjAFVOq_A.png",
          date: "2024．08．28",
        },
        {
          id: 6,
          title: this.$t('post6.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*Y8yyZ7mfWqM9DkBiEMyJQg.png",
          date: "2024．09．02",
        },
        {
          id: 7,
          title: this.$t('post7.core.title'),
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*yJi3pvZRfffeHToNDhtSmQ.png",
          date: "2024．09．08",
        },
        {
          id: 8,
          title: this.$t('post8.core.title'),
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*BoWK4m1ibJWviZh6U5rb4Q.png",
          date: "2024．09．12",
        },
        {
          id: 9,
          title: this.$t('post9.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*e2YufV1qOiEC3uTYnhQl2Q.png",
          date: "2024．09．20",
        },
        {
          id: 10,
          title: this.$t('post10.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/0*nGEzJ1WU_0eop9iQ.gif",
          date: "2024．09．30",
        },
        {
          id: 11,
          title: this.$t('post11.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/0*YBzjF3NbL3ATmRch.png",
          date: "2024．10．08",
        },
        {
          id: 12,
          title: this.$t('post12.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*FPPJYMZZ48qci9vCEW7n1A.png",
          date: "2024．10．14",
        },
        {
          id: 13,
          title: this.$t('post13.core.title'),
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*hbzy5hAo2iubtbZ5u8gHNg.png",
          date: "2024．10．26",
        },
        {
          id: 14,
          title: this.$t('post14.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*XmqGmjWlFW0ZdY8xyTCGqA.png",
          date: "2024．11．08",
        },
        {
          id: 15,
          title: this.$t('post15.core.title'),
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*l9LTo-VAunwN9UZeeoca4Q.png",
          date: "2024．11．17",
        },
        {
          id: 16,
          title: this.$t('post16.core.title'),
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*OT0pTyXTOhQ2tuQzuqSwwg.png",
          date: "2024．11．29",
        },
        {
          id: 17,
          title: this.$t('post17.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*FXqQSo8i5KrmhKGlImNUbA.png",
          date: "2024．12．15",
        },
        {
          id: 18,
          title: this.$t('post18.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*GxGNHeVOgVS_SFqGdY3TfQ.png",
          date: "2024．12．26",
        },
        {
          id: 19,
          title: this.$t('post19.core.title'),
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*VUK2az0HJHzilzN0Rpgv0A.png",
          date: "2025．01．18",
        },
      ];
    },
    currentCategory() {
      return this.$t('blog.item1'); // 返回當前語系的分類
    },
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
  data() {
    return {
      currentPage: 1,
      itemsPerPage: 12,
      currentCategory: this.$t('blog.item1'), // 初始設定分類
    };
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
    '$i18n.locale': {
      handler() {
        // 當語言切換時保持篩選器的分類
        this.currentCategory = this.$route.query.category || this.$t('blog.item1');
      }
    }
  },
};
</script>
