<template>
    <ul class="space-y-4 leading-loose list-none list-inside">
        <li v-for="(item, index) in items" :key="index" :class="customClass">
            <div class="flex gap-3 text-sm font-semibold md:text-base">
                <span 
                class="flex justify-center items-center w-6 h-6 text-xs text-center rounded md:h-8 md:w-8 md:text-sm"
                :class="numClass"
                >
                    0{{ index + 1 }}
                </span>
                <span class="w-full">
                {{ item.title }}
                </span>
            </div>
            <span class="block ml-8 sm:ml-10">
                {{ item.content }}
            </span>
        </li>
    </ul>
</template>

<script>
  export default {
    props: {
        items: {
            type: Array,
            required: true,
            default: () => [],
        },
        customClass: {
            type: String
        },
        numClass: {
            type: [String, Array],
            default: 'bg-B1 text-white dark:bg-stone-200 dark:text-stone-900'
        },
    },
  };
  </script>