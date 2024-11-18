<template>
    <div id="smooth-wrapper">
      <div id="smooth-content">
        <div class="mb-40">
          <ul class="grid gap-[6vw] pb-[calc(4*2em)]">
            <li 
              v-for="(card, index) in cards" 
              :key="index" 
              class="flex justify-center items-center transition-all duration-500 ease-in-out" 
              :class="[{ 'sticky': index === stickyIndex }, 'relative']" 
              ref="cardItems"
              :style="{ backgroundColor: cardColors[index] }"
            >
              <div class="w-full p-12 rounded-[3rem] shadow-xl text-center text-[#1c1c1c]">
                <h3>Card {{ index + 1 }}</h3>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { gsap } from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';
  
  export default {
    data() {
      return {
        cards: [1, 2, 3, 4], // Assuming you have 4 cards
        cardColors: ['#F79E1B', '#FF5733', '#00BCD4', '#4CAF50'], // Example colors, you can modify as needed
        stickyIndex: -1, // Index of the currently sticky card, -1 for none
        spacer: 20,
        minScale: 0.8,
      };
    },
    mounted() {
      gsap.registerPlugin(ScrollTrigger);
      this.initGSAP();
    },
    methods: {
      initGSAP() {
        const cards = this.$refs.cardItems;
  
        const distributor = gsap.utils.distribute({
          base: this.minScale,
          amount: 0.2,
        });
  
        cards.forEach((card, index) => {
          const scaleVal = distributor(index, cards.length, cards);
  
          gsap.to(card, {
            scrollTrigger: {
              trigger: card,
              start: 'top top',
              scrub: true,
            },
            ease: 'none',
            scale: scaleVal,
          });
  
          ScrollTrigger.create({
            trigger: card,
            start: `top-=${index * this.spacer} top`,
            endTrigger: '.card-container',
            end: `bottom top+=${200 + cards.length * this.spacer}`,
            pin: true,
            pinSpacing: false,
            invalidateOnRefresh: true,
            onToggle: self => {
              this.stickyIndex = self.isActive ? index : -1;
            },
          });
        });
      },
    },
  };
  </script>
  