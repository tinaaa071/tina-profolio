<template>
    <div
      ref="element"
      :class="[
        'transition-all duration-700 opacity-0', 
        animationClass, 
        isVisible ? 'opacity-100' : 'opacity-0'
      ]"
    >
      <slot />
    </div>
  </template>
  
  <script>
  import { ref, onMounted, onBeforeUnmount, computed } from 'vue';
  
  export default {
    props: {
      direction: {
        type: String,
        default: 'left',
        validator: (value) => ['left', 'right', 'top', 'bottom'].includes(value),
      },
    },
    setup(props) {
      const element = ref(null);
      const isVisible = ref(false);
  
      const animationClass = computed(() => {
        switch (props.direction) {
          case 'left':
            return isVisible.value ? 'translate-x-0' : '-translate-x-20';
          case 'right':
            return isVisible.value ? 'translate-x-0' : 'translate-x-20';
          case 'top':
            return isVisible.value ? 'translate-y-0' : '-translate-y-20';
          case 'bottom':
            return isVisible.value ? 'translate-y-0' : 'translate-y-20';
          default:
            return 'translate-x-0';
        }
      });
  
      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              isVisible.value = true;
            } else {
              isVisible.value = false;
            }
          });
        },
        { threshold: 0.1 }
      );
  
      onMounted(() => {
        if (element.value) observer.observe(element.value);
      });
  
      onBeforeUnmount(() => {
        if (element.value) observer.unobserve(element.value);
      });
  
      return { element, isVisible, animationClass };
    },
  };
  </script>
  