<template>
  <div 
    v-if="showModalBtn"
    @click.stop="openModal"
    role="button"
    tabindex="0"
    class="cursor-pointer group"
  >
    <div class="overflow-hidden relative w-full rounded-lg aspect-video dark:border dark:border-white/20">
      <div class="absolute right-4 bottom-4 z-10 px-1.5 py-1 text-xs font-normal whitespace-nowrap rounded bg-stone-50 text-stone-600">
        {{ modal.category }}
      </div>
      <img 
        v-if="modal.image"
        :src="modal.image" 
        :alt="modal.title" 
        class="object-cover object-center w-full h-full transition-all duration-300 ease-in-out group-hover:scale-110"
      />
      <Lottie 
      v-if="modal.lottiePath"
      :path="modal.lottiePath" 
      class="object-cover object-center w-full h-full transition-all duration-300 ease-in-out group-hover:scale-110"
      heightClass="h-full" 
      widthClass="w-full"
      />
    </div>
    
    <p class="px-2 py-2 text-base font-medium text-justify md:text-sm xl:text-base xl:px-4 line-clamp-3 dark:text-white">
      {{ modal.title }}
    </p>
  </div>
</template>

<script>
export default {
  name: "ModalItem",
  props: {
    modalId: {
      type: [String, Number],
      required: true
    },
    modal: {
      type: Object,
      required: true
    },
    showModalBtn: {
      type: Boolean,
      default: true
    }
  },
  methods: {
    openModal() {
      this.$emit('open-modal', this.modalId);
    }
  }
};
</script>
