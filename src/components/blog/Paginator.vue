<template>
  <div class="flex justify-center items-center text-center text-stone-900 dark:text-white">
    <!-- <button
      @click="goToPage(1)"
      :disabled="currentPage === 1"
      class="px-3 py-1 bg-gray-200 hover:bg-gray-300 disabled:cursor-not-allowed disabled:opacity-50"
    >
      First
    </button> -->
    
    <!-- Previous Button -->
    <button
      @click="goToPage(currentPage - 1)"
      :disabled="currentPage === 1"
      class="inline-block p-2 text-lg align-middle rounded-lg hover:bg-B3 disabled:cursor-not-allowed disabled:opacity-50 dark:hover:bg-stone-600"
    >
      <OcticonChevronLeft24 />
    </button>

    <!-- Render page numbers and the more icon -->
    <span
      v-for="(page, index) in pagesToShow"
      :key="index"
      class="inline-block px-3.5 py-1.5 align-middle rounded-lg cursor-pointer"
      :class="{
        ' bg-B3 text-B1 dark:bg-stone-600 dark:text-white': currentPage === page,
        ' hover:bg-B3 dark:hover:bg-stone-700': currentPage !== page,
      }"
      @click="page !== 'more' && goToPage(page)"
    >
      <template v-if="page === 'more'">
        <RiMoreLine />
      </template>
      <template v-else>
        {{ page }}
      </template>
    </span>

    <!-- Next Button -->
    <button
      @click="goToPage(currentPage + 1)"
      :disabled="currentPage === totalPages"
      class="inline-block p-2 text-lg align-middle rounded-lg hover:bg-B3 disabled:cursor-not-allowed disabled:opacity-50 dark:hover:bg-stone-600"
    >
      <OcticonChevronRight24 />
    </button>
    
    <!-- <button
      @click="goToPage(totalPages)"
      :disabled="currentPage === totalPages"
      class="px-3 py-1 bg-gray-200 hover:bg-gray-300 disabled:cursor-not-allowed disabled:opacity-50"
    >
      Last
    </button> -->
  </div>
</template>

<script>
export default {
  props: {
    totalItems: {
      type: Number,
      required: true,
    },
    itemsPerPage: {
      type: Number,
      required: true,
    },
    currentPage: {
      type: Number,
      required: true,
    },
  },
  computed: {
    totalPages() {
      // 確保至少有 1 頁
      return Math.max(Math.ceil(this.totalItems / this.itemsPerPage), 1);
    },
    pagesToShow() {
      // 保證 pagesToShow 至少包含 1
      const pages = [];
      for (let i = 1; i <= this.totalPages; i++) {
        pages.push(i);
      }
      return pages;
    },
  },
  methods: {
    goToPage(page) {
      if (page >= 1 && page <= this.totalPages) {
        this.$emit('page-changed', page);
      }
    },
  },
};
</script>
