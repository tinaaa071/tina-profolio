<template>
  <RouterLink :to="linkTo" class="">
      <div 
          :class="[
              'flex overflow-hidden relative justify-center items-center rounded-full group w-fit border-2',
              borderClass
          ]" 
          @mouseover="toggleHover(true)" 
          @mouseleave="toggleHover(false)"
      >
          <div 
              :class="[
                  textClass, 
                  'z-10 relative transition-colors ease-in-out duration-300', hoverTextClass,
                  { 'hovered': isHovered }
              ]"
              class="inline-flex items-center px-4 py-2.5 text-sm font-bold sm:px-6 sm:py-3.5"
          >
              {{ text }}
              <mingcute-arrow-right-line class="ml-2 text-lg" />
          </div>
          <div 
              :class="[
                  'absolute top-0 flex items-center justify-center w-full h-full rounded-full z-1 -left-[100%] card-content',
                  { 'is-hovered': isHovered }
              ]" 
              style="transition: transform 0.4s, left 0.4s"
          >
              <div :class="[bgClass, 'flex justify-center items-center w-full h-full rounded-full text-stone-900']">
              </div>
          </div>
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
  text: {
    type: String,
    required: true,
  },
  borderClass: {
    type: String,
    default: 'border-white', // Default value if no border is provided
  },
  textClass: {
    type: String,
    default: 'text-white', // Default text color
  },
  hoverTextClass: {
    type: String,
    default: 'group-hover:text-stone-900', // Default text color
  },
  bgClass: {
    type: String,
    default: 'bg-white', // Default background color
  },
},
data() {
  return {
    isHovered: false,
  };
},
methods: {
  toggleHover(status) {
    this.isHovered = status;
  },
},
};
</script>

<style scoped>
@keyframes shake {
100% { transform: translateX(0); }
20% { transform: translateX(-120px); }
40% { transform: translateX(120px); }
60% { transform: translateX(-80px); }
80% { transform: translateX(40px); }
}

.card-content.is-hovered {
left: 0;
animation: shake 0.8s ease-in-out;
}
</style>
