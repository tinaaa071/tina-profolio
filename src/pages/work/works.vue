<template>
  <div class="bg-white sm:pb-10 dark:bg-stone-900 text-stone-900">
    <Navbar />
    <ProgressBar />
    <BackToTop class="z-20" />
    <div class="pt-24 pb-6 mx-auto min-h-screen sm:pt-28 md:pt-32">
      <Tabs
        :currentCategory="currentCategory"
        :categories="categories"
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
      currentCategory: this.$t('tag.item1'), // Default category
      currentPage: 1,
      itemsPerPage: 12,
    };
  },
  computed: {
    // Dynamically generate categories based on the current language
    categories() {
      return [
        this.$t('tag.item1'),
        this.$t('tag.item2'),
        this.$t('tag.item3'),
        this.$t('tag.item4'),
        this.$t('tag.item5'),
        this.$t('tag.item6'),
        this.$t('tag.item7'),
      ];
    },
    // Dynamically generate posts based on the current language
    posts() {
      return [
        {
          id: 1,
          title: this.$t('project1.core.title'),
          category: [this.$t('tag.item2'), this.$t('tag.item3')],
          image: 'https://i.imgur.com/8cDMtnX.png',
          date: '2023．10．02',
          link: '/work/project1',
        },
        {
          id: 2,
          title: this.$t('project2.core.title'),
          category: [this.$t('tag.item2'), this.$t('tag.item3')],
          image: 'https://i.imgur.com/CrxmhKx.png',
          date: '2023．10．02',
          link: '/work/project2',
        },
        {
          id: 3,
          title: this.$t('project3.core.title'),
          category: [this.$t('tag.item2'), this.$t('tag.item3'), this.$t('tag.item6')],
          image: 'https://i.imgur.com/VyAFrb6.png',
          date: '2024．06．30',
          link: '/work/project3',
        },
        {
          id: 4,
          title: this.$t('project4.core.title'),
          category: [this.$t('tag.item2'), this.$t('tag.item3'), this.$t('tag.item5'), this.$t('tag.item7')],
          image: 'https://i.imgur.com/saj60S3.png',
          date: '2024．11．20',
          link: '/work/project4',
        },
        {
          id: 5,
          title: this.$t('project5.core.title'),
          category: [this.$t('tag.item2'), this.$t('tag.item4'), this.$t('tag.item6')],
          image: 'https://i.imgur.com/EBTQHuz.png',
          date: '2024．11．20',
          link: '/work/project5',
        },
      ];
    },
    // Filter posts based on the selected category
    filteredPosts() {
      if (this.currentCategory === this.$t('tag.item1')) {
        return this.posts;
      }
      return this.posts.filter(post =>
        post.category.includes(this.currentCategory) // Check if category matches
      );
    },
    // Paginate the filtered posts
    paginatedPosts() {
      const start = (this.currentPage - 1) * this.itemsPerPage;
      const end = start + this.itemsPerPage;
      return this.filteredPosts.slice(start, end);
    },
  },
  watch: {
    // Watch for changes in language to trigger reactivity in posts and categories
    '$i18n.locale': 'updateTranslations',
  },
  methods: {
    // Update translations when language changes
    updateTranslations() {
      this.currentCategory = this.$t('tag.item1'); // Reset the category to default
    },
    handlePageChange(page) {
      this.currentPage = page;
    },
    // Change category and reset page number when category changes
    filterByCategory(category) {
      this.currentCategory = category;
      this.currentPage = 1;
    },
  },
};
</script>
