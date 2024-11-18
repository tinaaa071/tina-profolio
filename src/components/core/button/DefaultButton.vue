<template>
  <RouterLink :to="linkTo" 
  class="flex justify-center items-center px-4 py-2.5 text-center rounded-full border-2 transition-colors duration-300 ease-in-out"
  >
    <!-- Left Icon -->
    <div v-if="showLeftIcon" class="mr-2">
        <component :is="icon" />
    </div>
    <!-- text -->
    <p>
        {{ text }}
    </p>
    <!-- Right Icon -->
    <div v-if="showRightIcon" class="ml-2">
        <component :is="icon" />
    </div>
  </RouterLink>
</template>

<script>
export default {
    props: {
        linkTo: {
            type: String,
            required: true,
        },
        showLeftIcon: {
            type: Boolean,
            default: false,
        },
        showRightIcon: {
            type: Boolean,
            default: false,
        },
        icon: {
            type: [Object, Function],
            required: true,
        },
        text: {
            type: String,
            required: true,
        },
    },
};
</script>