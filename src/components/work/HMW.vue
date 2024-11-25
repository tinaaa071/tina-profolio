<template>
    <div class="relative mb-8 xl:mb-12">
        <Fa6SolidQuoteLeft class="absolute -top-6 left-6 text-5xl text-B2 dark:text-stone-300" />
        <Fa6SolidQuoteRight class="absolute right-6 -bottom-6 text-5xl text-B2 dark:text-stone-300" />
        <div class=" px-10 py-8 xl:px-16 xl:py-12 space-y-6 text-white rounded-[40px] xl:rounded-[56px] bg-stone-900 dark:bg-white dark:text-stone-900">
            <p class="text-center">
            {{ $t('work.title.item6') }}
            </p>
            <p class="font-normal">
            {{ text }}
            </p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        text: {
            type: String,
        }
  },
}
</script>