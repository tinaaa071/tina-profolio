<template>
    <div class="relative mt-2 mb-8 md:mb-12">
        <Fa6SolidQuoteLeft class="absolute -top-5 left-6 text-3xl sm:text-4xl text-B2 dark:text-stone-300" />
        <Fa6SolidQuoteRight class="absolute -bottom-5 right-6 text-3xl sm:text-4xl text-B2 dark:text-stone-300" />
        <div class=" p-8 lg:p-12 space-y-4 sm:space-y-6 text-white rounded-[40px] lg:rounded-[56px] bg-stone-900 dark:bg-white dark:text-stone-900">
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