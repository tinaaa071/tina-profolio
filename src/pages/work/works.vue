<template>
  <div class="bg-white sm:pb-10 dark:bg-stone-900 text-stone-900">
    <Navbar />
    <ProgressBar />
    <BackToTop class="z-20" />
    <div class="pt-24 pb-6 mx-auto min-h-screen sm:pt-28 md:pt-32">
      <Tabs
        :currentCategory="currentCategory"
        :categories="[
          $t('tag.item1'),
          $t('tag.item2'),
          $t('tag.item3'),
          $t('tag.item4'),
          $t('tag.item5'),
          $t('tag.item6'),
          $t('tag.item7'),
        ]"
        @category-changed="filterByCategory"
      />

      <div class="px-6 sm:px-10 xl:px-28">
        <!-- Display "No data" message if no posts are available -->
        <div v-if="filteredPosts.length === 0" class="p-4 text-center">
          No data
        </div>

        <!-- Display WorkList and Paginator only if there are posts -->
        <div v-else>
          <WorkList :posts="paginatedPosts" />

          <Paginator
            :totalItems="filteredPosts.length"
            :itemsPerPage="itemsPerPage"
            :currentPage="currentPage"
            @page-changed="handlePageChange"
          />
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
          titleKey: 'project1.core.title',
          categoryKeys: ['tag.item2', 'tag.item3'],
          image: 'https://i.imgur.com/8cDMtnX.png',
          date: '2023．10．02',
          link: '/work/project1',
        },
        {
          id: 2,
          titleKey: 'project2.core.title',
          categoryKeys: ['tag.item2', 'tag.item3'],
          image: 'https://i.imgur.com/CrxmhKx.png',
          date: '2023．10．02',
          link: '/work/project2',
        },
        {
          id: 3,
          titleKey: 'project3.core.title',
          categoryKeys: ['tag.item2', 'tag.item3', 'tag.item6'],
          image: 'https://i.imgur.com/VyAFrb6.png',
          date: '2024．06．30',
          link: '/work/project3',
        },
        {
          id: 4,
          titleKey: 'project4.core.title',
          categoryKeys: ['tag.item2', 'tag.item3', 'tag.item5', 'tag.item7'],
          image: 'https://i.imgur.com/saj60S3.png',
          date: '2024．11．20',
          link: '/work/project4',
        },
        {
          id: 5,
          titleKey: 'project5.core.title',
          categoryKeys: ['tag.item2', 'tag.item4', 'tag.item6'],
          image: 'https://i.imgur.com/EBTQHuz.png',
          date: '2024．11．20',
          link: '/work/project5',
        },
      ],
      currentPage: 1,
      itemsPerPage: 12,
      currentCategoryKey: 'tag.item1', // 預設類別的 key
    };
  },
  computed: {
    translatedPosts() {
      return this.posts.map((post) => ({
        ...post,
        title: this.$t(post.titleKey),
        category: post.categoryKeys.map((key) => this.$t(key)),
      }));
    },
    filteredPosts() {
      const currentCategory = this.$t(this.currentCategoryKey);
      if (currentCategory === this.$t('tag.item1')) {
        return this.translatedPosts;
      }
      return this.translatedPosts.filter((post) =>
        post.category.includes(currentCategory)
      );
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
    filterByCategory(categoryKey) {
      this.currentCategoryKey = categoryKey;
      this.currentPage = 1; // 切換分類時回到第一頁
    },
  },
};
</script>
