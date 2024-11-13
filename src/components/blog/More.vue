<template>
    <div class="block px-6 py-8 bg-B3 dark:bg-stone-800 dark:border-t dark:border-white/20 sm:px-10 md:py-10" 
    v-if="showMore"
    >
      <div class="flex flex-col gap-6 mx-auto max-w-3xl">
        <div class="flex gap-4 items-center xs:gap-4">
          <p class="dark:text-white">
            {{ $t('work.core.item1') }}
          </p>
          <hr class="w-full border-stone-900 dark:border-white">
        </div>
        <div class="grid grid-cols-2 gap-4 xs:grid-cols-4 h-fit">
          <PostCard 
            v-for="post in sortedAndLimitedPosts" 
            :key="post.id" 
            :post="post" 
            :showTag="true"
            :linkTo="post.link"
            aspectRatio="aspect-[4/5] group-hover:-translate-y-1 transition-transform duration-200 rounded-3xl"
          />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      posts: {
        type: Array,
        required: true
      },
      showMore: {
        type: Boolean,
        required: true
      }
    },
    computed: {
      sortedAndLimitedPosts() {
        // Assuming 'date' is the property that determines the post's recency
        return this.posts
          .slice()  // Create a shallow copy of the array to avoid mutating the original array
          .sort((a, b) => new Date(b.date) - new Date(a.date))  // Sort posts by date, newest first
          .slice(0, 8);  // Limit to the top 8 posts
      }
    }
  };
  </script>
  