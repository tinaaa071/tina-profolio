<template>
    <div class="overflow-hidden rounded-2xl border shadow sm:rounded-3xl border-B4">
      <!-- Title -->
      <button
        @click="toggle"
        :class="{
          'bg-B4 text-B1 dark:bg-stone-800 dark:border-b dark:border-white dark:text-white ': isOpen,
          'bg-stone-50 text-stone-600 dark:bg-transparent dark:text-stone-300 ': !isOpen
        }"
        class="flex overflow-hidden relative items-center px-4 py-3 w-full text-left transition-colors duration-300 ease-in-out xs:justify-between sm:px-5 sm:py-4 hover:bg-B4"
      >
        <div class="flex gap-4 items-center font-medium">
          <!-- Logo -->
          <img
            v-if="showLogo"
            :src="logoSrc"
            alt="logo"
            class="object-cover w-16 h-16 rounded-2xl border border-white"
          />
          <!-- Company -->
          <div class="flex flex-col gap-2 font-medium">
            <!-- Title -->
            <p class="font-semibold">
                {{ title }}
            </p>
            <!-- Info -->
            <p class="font-normal">
                {{ info }} <span class="px-1">|</span> {{ time }}
            </p>
            <!-- Desc -->
            <p class="text-sm font-normal">
                {{ desc }}
            </p>
          </div>
        </div>
        <PlusButton :isPlus="!isOpen" @toggle="toggle" 
        class="absolute top-4 right-4 z-10 xs:static"
        />
      </button>
      <!-- Content -->
      <TransitionFade>
        <div v-show="isOpen" class="p-6 space-y-6 bg-white dark:bg-transparent">
        <!-- Inner -->
        <div class="flex">
          <div v-for="(section, index) in sections" :key="index" class="grow">
            <p class="mb-2 text-stone-800 dark:text-white">
              {{ section.listTitle }}
            </p>
            <ul class="font-normal list-disc list-inside text-stone-500 dark:text-stone-400">
              <li v-for="(item, index) in section.listItems" :key="index">
                {{ item }}
              </li>
            </ul>
          </div>
        </div>
        <!-- Attachment -->
        <div 
        v-if="showAtt"
        class="grid grid-cols-2 gap-2 md:gap-4 sm:grid-cols-4"
        >
          <Attachment
            v-for="item in items"
            :key="item.id"
            :modalId="item.id"
            :imgSrc="item.imgSrc"
            :linkTo="item.linkTo"
            :showModalBtn="item.showModalBtn"
            :showLinkBtn="item.showLinkBtn"
            @open-modal="openModal"
          />
          <Modal
            v-if="currentModalId !== null"
            :show="currentModalId !== null"
            @close="closeModal"
          >
          <img 
            class="w-full aspect-video rounded-3xl h-[500px]"
            src="https://images.unsplash.com/photo-1628766416710-61d6f15f32b9?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" 
            alt="">
          </Modal>
        </div>
      </div>
      </TransitionFade>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    props: {
    title: {
      type: String,
      required: true,
    },
    info: {
      type: String,
      required: true,
    },
    time: {
      type: String,
      required: true,
    },
    desc: {
      type: String,
      required: true,
    },
    showLogo: {
      type: Boolean,
      default: false,
    },
    logoSrc: {
      type: String,
      default: '',
    },
    sections: {
      type: Array,
      required: true,
      default: () => []
    },
    showAtt: {
        type: Boolean,
        default: true
      },
    items: {
      type: Array,
      required: true,
    }
  },
  setup(props, { emit }) {
    const isOpen = ref(false);
    const currentModalId = ref(null);

    const toggle = () => {
      isOpen.value = !isOpen.value;
    };

    const openModal = (modalId) => {
      currentModalId.value = modalId;
    };

    const closeModal = () => {
      currentModalId.value = null;
    };

    return {
      isOpen,
      toggle,
      currentModalId,
      openModal,
      closeModal
    };
  }
  };
  </script>
  
  <style scoped>
  /* Assuming TransitionFade is a defined transition */
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.5s ease, transform 0.5s ease;
  }
  
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
    transform: translateY(-10px);
  }
  
  </style>
  