<template>
  <div class="overflow-hidden relative w-full h-96">
    <div
      ref="zoomElement"
      class="w-full h-full bg-center bg-cover"
      :style="{ backgroundImage: 'url(' + imageUrl + ')' }"
    ></div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

// Define props to receive the image URL from the parent component
const props = defineProps({
  imageUrl: {
    type: String,
    required: true,
  },
})

const zoomElement = ref(null)

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger)

  gsap.fromTo(
    zoomElement.value,
    {
      scale: 1,
    },
    {
      scale: 1.5, // Maximum zoom scale
      scrollTrigger: {
        trigger: zoomElement.value,
        start: 'top 20%', // Start when the element enters the viewport
        end: 'bottom 30%', // End when the element leaves the viewport
        scrub: true, // Enable smooth scroll effect
      },
    }
  )
})
</script>

<style scoped>
/* Ensure the element fills its container */
div {
  position: relative;
}

div > div {
  transition: transform 0.5s ease;
}
</style>
