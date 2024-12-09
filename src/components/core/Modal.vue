<template>
    <TransitionFade name="fade">
      <div
        v-if="show"
        class="flex fixed inset-0 z-50 justify-center items-center p-6 w-full text-right backdrop-blur-lg bg-black/30"
        @click="handleOverlayClick"
      >
        <div
          class="relative mx-auto w-full sm:max-w-5xl"
          @click.stop
        >
        <button
            type="button"
            class="p-3 mb-4 text-white rounded-xl border-2 border-white transition-colors bg-white/10 group hover:bg-white/15"
            @click="$emit('close')"
          >
            <span class="sr-only">Close</span>
            <fa6-solid-xmark class="transition-all duration-200 ease-in-out group-hover:rotate-90" />
          </button>
          
          <slot></slot>
        </div>
      </div>
    </TransitionFade>
  </template>
  
<script setup>
import { onMounted, onBeforeUnmount, watch } from 'vue';
const props = defineProps({
show: Boolean
});

const emit = defineEmits(['close']);

const handleOverlayClick = () => {
emit('close');
};

const lockScroll = () => {
  document.body.style.overflow = 'hidden';
};

const unlockScroll = () => {
  document.body.style.overflow = '';
};

watch(
  () => props.show,
  (newVal) => {
    if (newVal) {
      lockScroll();
    } else {
      unlockScroll();
    }
  }
);

onBeforeUnmount(() => {
  unlockScroll();
});
</script>
  