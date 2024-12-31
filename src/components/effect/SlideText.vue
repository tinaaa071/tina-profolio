<template>
    <div 
    class="inline-block overflow-hidden relative h-7 align-bottom"
    
    >
        <span 
        class="block vslide" 
        v-for="(text, index) in texts" 
        :key="index" 
        >
         {{ text }}
        </span>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        texts: [
          'Researcher',
          'UI/UX Designer',
          'Product Designer',
          'Tina Chen',
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  @keyframes animateWords {
    0% { transform: translateY(0%); }
    20% { transform: translateY(-100%); }
    40% { transform: translateY(-100%); }
    60% { transform: translateY(-200%); }
    70% { transform: translateY(-200%); }
    85% { transform: translateY(-300%); }
    100% { transform: translateY(-300%); }
  }

  
  .vslide {
    animation: animateWords 4s infinite ease;
  }
  

  </style>
  