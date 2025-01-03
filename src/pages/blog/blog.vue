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
          date: "2024．09．02",
        },
        {
          id: 2,
          title: this.$t('post2.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*Qjgp1iIbw1IY2ww1AxfbPg.png",
          date: "2024．09．10",
        },
        {
          id: 3,
          title: this.$t('post3.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*ckOnmeIa3T-ASRMF1oGolg.png",
          date: "2024．09．17",
        },
        {
          id: 4,
          title: this.$t('post4.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*hx609LG91bVhVTfCBCf_bA.png",
          date: "2024．09．24",
        },
        {
          id: 5,
          title: this.$t('post5.core.title'),
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*kAq2lKvc-rZtuvjAFVOq_A.png",
          date: "2024．10．05",
        },
        {
          id: 6,
          title: this.$t('post6.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*Y8yyZ7mfWqM9DkBiEMyJQg.png",
          date: "2024．10．16",
        },
        {
          id: 7,
          title: this.$t('post7.core.title'),
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*yJi3pvZRfffeHToNDhtSmQ.png",
          date: "2024．10．20",
        },
        {
          id: 8,
          title: this.$t('post8.core.title'),
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*BoWK4m1ibJWviZh6U5rb4Q.png",
          date: "2024．10．28",
        },
        {
          id: 9,
          title: this.$t('post9.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*e2YufV1qOiEC3uTYnhQl2Q.png",
          date: "2024．11．01",
        },
        {
          id: 10,
          title: this.$t('post10.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/0*nGEzJ1WU_0eop9iQ.gif",
          date: "2024．11．02",
        },
        {
          id: 11,
          title: this.$t('post11.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/0*YBzjF3NbL3ATmRch.png",
          date: "2024．11．03",
        },
        {
          id: 12,
          title: this.$t('post12.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*FPPJYMZZ48qci9vCEW7n1A.png",
          date: "2024．11．05",
        },
        {
          id: 13,
          title: this.$t('post13.core.title'),
          category: this.$t('blog.item5'),
          image: "https://cdn-images-1.medium.com/max/1600/1*hbzy5hAo2iubtbZ5u8gHNg.png",
          date: "2024．11．06",
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
          date: "2024．11．12",
        },
        {
          id: 16,
          title: this.$t('post16.core.title'),
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*OT0pTyXTOhQ2tuQzuqSwwg.png",
          date: "2024．11．13",
        },
        {
          id: 17,
          title: this.$t('post17.core.title'),
          category: this.$t('blog.item4'),
          image: "https://cdn-images-1.medium.com/max/1600/1*FXqQSo8i5KrmhKGlImNUbA.png",
          date: "2024．11．15",
        },
        {
          id: 18,
          title: this.$t('post18.core.title'),
          category: this.$t('blog.item2'),
          image: "https://cdn-images-1.medium.com/max/1600/1*GxGNHeVOgVS_SFqGdY3TfQ.png",
          date: "2024．11．16",
        },
        {
          id: 19,
          title: this.$t('post19.core.title'),
          category: this.$t('blog.item3'),
          image: "https://cdn-images-1.medium.com/max/1600/1*VUK2az0HJHzilzN0Rpgv0A.png",
          date: "2024．11．18",
        },
      ];
    },
    currentPage() {
      return parseInt(this.$route.query.page) || 1;
    },
    itemsPerPage() {
      return 12;
    },
    currentCategory() {
      return this.$route.query.category || this.$t('blog.item1');
    },
    filteredPosts() {
      let posts = this.currentCategory === this.$t('blog.item1')
        ? this.posts
        : this.posts.filter((post) => post.category === this.currentCategory);

      // Sort posts by date from newest to oldest
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
      this.$router.push({ path: this.$route.path, query: { ...this.$route.query, page } });
    },
    filterByCategory(category) {
      this.$router.push({ path: this.$route.path, query: { ...this.$route.query, category, page: 1 } });
    },
  },
};
</script>
