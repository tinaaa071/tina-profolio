<template>
    <ul class="space-y-4 leading-loose list-none list-inside">
        <li v-for="(item, index) in items" :key="index">
            <div class="flex gap-3 font-semibold">
                <span class="w-8 h-8 text-center text-white rounded bg-B1 dark:bg-stone-200 dark:text-stone-900">
                    {{ index + 1 }}
                </span>
                <span class="w-full">
                {{ item.title }}
                </span>
            </div>
            <span class="block ml-10">
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
    },
  };
  </script>