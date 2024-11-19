<template>
    <div id="smooth-wrapper">
      <div id="smooth-content">
        <div class="card-container">
          <ul class="card-stack">
            <li v-for="(card, index) in cards" :key="index" class="card-item" ref="cardItems" :class="{ 'sticky': index === stickyIndex }">
              <div :class="['card-body', cardColor[index]]">
                <!-- Slot for dynamic content inside card-body -->
                <slot :name="'card' + index">
                </slot>
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
        cards: [1, 2], // Assuming you have 4 cards
        cardColor: [
        'bg-stone-900 dark:bg-B3', // Tailwind color classes
        'bg-B3 dark:bg-stone-700',
      ],
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
              markers: false,
            },
            ease: 'none',
            scale: scaleVal,
          });
  
          ScrollTrigger.create({
            trigger: card,
            start: `top-=${index * this.spacer} top`,
            endTrigger: '.card-container',
            end: `bottom top+=${500 + cards.length * this.spacer}`,
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
  
  <style scoped>
  :root {
    --cardHeight: 200px;
    --cardTopPadding: 2em;
    --cardMargin: 6vw;
  }
  
  .card-stack {
    @apply list-none grid grid-cols-1 gap-[var(--cardMargin)] pb-[calc(var(--cards)*var(--cardTopPadding))] mb-[var(--cardMargin)];
  }
  
  .card-item {
    position: relative;
  }
  
  .card-item.sticky {
    transform: scale(1);
  }
  
  .card-body {
    @apply p-6 rounded-2xl xl:rounded-3xl w-full;
  }
  </style>
  