<template>
    <Section
      class="flex flex-col items-center px-6 pt-8 pb-12 w-full text-center md:py-16"
    >
      <!-- Title -->
      <p class="mb-6 text-sm font-semibold md:text-lg text-stone-500 md:mb-8 dark:text-white">
        {{ $t('work.next.item1') }}
      </p>
      <!-- Project -->
      <p
        :class="[
          'mb-6 text-xl sm:text-4xl font-semibold transition-colors duration-300 ease-in-out',
          isHovered ? 'text-stone-300 dark:text-stone-500 blur-sm' : 'text-stone-500 dark:text-stone-300'
        ]"
      >
        {{ title }}
      </p>
      <!-- Project -->
      <div class="flex relative justify-center w-full h-44 sm:h-72 xl:h-96">
        <CursorDot />
        <!-- Img -->
        <RouterLink
          :to="linkTo"
          class="w-[280px] sm:w-[420px] xl:w-[560px] absolute bottom-0 z-0 transition-all duration-300 ease-in-out transform -translate-x-1/2 left-1/2  md:hover:bottom-20 hover:bottom-6 xs:hover:bottom-8 sm:hover:bottom-12"
          @mouseover="isHovered = true"
          @mouseleave="isHovered = false"
        >
          <img
            src="https://images.unsplash.com/photo-1688297969982-2d46e66ba2f2?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
            alt=""
            class="rounded-2xl aspect-video md:rounded-3xl"
          />
        </RouterLink>
        <!-- Mask -->
        <div
          class="absolute bottom-0 z-10 mx-auto w-full h-20 bg-white border-t xs:w-9/12 md:w-2/3 lg:w-1/2 dark:bg-stone-900 border-B2/70 md:h-32"
        ></div>
        <!-- Button -->
      <MagneticButton
        linkTo="/"
        :icon="icon"
        :showIcon="showIcon"
        :text="$t('work.next.item2')"
        class="absolute bottom-0 z-10"
      />
      </div>
    </Section>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        required: true,
      },
      linkTo: {
        type: String,
        required: true,
      },
      icon: {
        type: [Object, Function],
        required: true,
      },
      showIcon: {
        type: Boolean,
        default: true,
      },
    },
    data() {
      return {
        isHovered: false, // State to track hover
      };
    },
  };
  </script>
  