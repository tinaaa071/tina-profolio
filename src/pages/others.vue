<template>
    <div class="bg-white sm:pb-10 dark:bg-stone-900 text-stone-900">
      <Navbar />
      <ProgressBar />
      <BackToTop class="z-20" />
      <div class="pt-24 pb-6 mx-auto min-h-screen sm:pt-28 md:pt-32">
        <Tabs
          :currentCategory="currentCategory"
          :categories="[
            $t('other.item1'),
            $t('other.item2'),
            $t('other.item3'),
            $t('other.item4'),
            $t('other.item5'),
          ]"
          @category-changed="filterByCategory"
        />
  
        <div class="px-6 sm:px-10 xl:px-28">
          <div v-if="filteredPosts.length === 0" class="p-4 text-center">
            No data
          </div>
  
          <div v-else>
            <ModalList
              :modals="paginatedPosts"
              @open-modal="openModal"
            />
  
            <Paginator
              :totalItems="filteredPosts.length"
              :itemsPerPage="itemsPerPage"
              :currentPage="currentPage"
              @page-changed="handlePageChange"
            />
          </div>
        </div>
      </div>
  
      <Modal
        v-if="currentModalId !== null"
        :show="currentModalId !== null"
        @close="closeModal"
        :modal="getModalById(currentModalId)"
      >
      <div v-if="getModalById(currentModalId)?.lottiePath">
        <!-- Lottie Animation -->
        <Lottie
        class="w-full aspect-video rounded-3xl h-[500px] object-cover object-center"
          :path="getModalById(currentModalId)?.lottiePath"
          
        />
      </div>
      <div v-else>
        <!-- Image -->
        <img
          class="w-full aspect-video rounded-3xl h-[500px] object-cover object-center"
          :src="getModalById(currentModalId)?.image"
          alt="Modal Image"
        />
      </div>
      </Modal>
    </div>
    <Footer />
  </template>
  
  <script>
export default {
  data() {
    return {
      currentPage: 1,
      itemsPerPage: 12,
      currentCategory: this.$t('other.item1'),
      currentModalId: null // Track the current open modal ID
    };
  },
  computed: {
    modals() {
      return [
        {
          id: 1,
          title: this.$t('other.title.item1'),
          category: this.$t('other.item4'),
          lottiePath: "https://lottie.host/9ff43bd5-4052-4f5d-a3df-563e5fb89681/QWbSsou0iJ.json"
        },
        {
          id: 2,
          title: this.$t('other.title.item2'),
          category: this.$t('other.item4'),
          lottiePath: "https://lottie.host/c74a5323-70cd-49bb-bf4f-330c0f16018a/NZyeJAfs6d.json"
        },
        {
          id: 3,
          title: "Post 1",
          category: this.$t('other.item3'),
          image: "https://images.unsplash.com/photo-1725628736546-6b334a2002d7?q=80&w=2787&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
        },
        {
          id: 4,
          title: this.$t('other.title.item3'),
          category: this.$t('other.item4'),
          lottiePath: "https://lottie.host/8b4dae31-4a4a-4996-bd37-c3a86ae7006a/pTng0tWY0t.json"
        },
        {
          id: 5,
          title: this.$t('other.title.item4'),
          category: this.$t('other.item4'),
          lottiePath: "https://lottie.host/919405a9-98e0-467c-8e62-196bc1f84c11/7o6pesu7Q4.json"
        },
        {
          id: 6,
          title: this.$t('other.title.item5'),
          lottiePath: "https://lottie.host/136b3517-5777-475f-a328-01cc7737d2b5/fgd0wFcaRp.json"
        }
      ];
    },
    filteredPosts() {
      if (this.currentCategory === this.$t('other.item1')) {
        return this.modals;
      }
      return this.modals.filter(
        (post) => post.category === this.currentCategory
      );
    },
    paginatedPosts() {
      const start = (this.currentPage - 1) * this.itemsPerPage;
      const end = start + this.itemsPerPage;
      return this.filteredPosts.slice(start, end);
    }
  },
  watch: {
    // Watch for language change to reset the category and page
    $i18n: {
      handler() {
        this.currentCategory = this.$t('other.item1');
        this.currentPage = 1; // Reset to the first page when language changes
      },
      deep: true
    }
  },
  methods: {
    handlePageChange(page) {
      this.currentPage = page;
    },
    filterByCategory(category) {
      this.currentCategory = category;
      this.currentPage = 1; // Reset to the first page when changing category
    },
    openModal(modalId) {
      this.currentModalId = modalId;
    },
    closeModal() {
      this.currentModalId = null;
    },
    getModalById(id) {
      return this.modals.find(modal => modal.id === id);
    }
  }
};
</script>
