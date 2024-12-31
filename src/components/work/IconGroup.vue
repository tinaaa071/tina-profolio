<!-- src/components/IconGroup.vue -->
<template>
    <div class="flex flex-col justify-items-center items-center space-y-4 text-2xl text-white sm:space-y-5">
        <!-- <fa6-solid-envelope v-if="iconsVisible[0]" aria-hidden="true" /> -->
        <Icon 
        imageUrl="https://i.imgur.com/7pnxjJF.png"
        tooltipText="Figma"
        v-if="iconsVisible[0]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/zIeXvD3.png"
        tooltipText="Vue"
        v-if="iconsVisible[1]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/28m1SmQ.png"
        tooltipText="Vite"
        v-if="iconsVisible[2]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/szgrbI5.png"
        tooltipText="Git"
        v-if="iconsVisible[3]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/HAqgRy7.png"
        tooltipText="Tailwind"
        v-if="iconsVisible[4]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/kAMkFzO.png"
        tooltipText="Notion"
        v-if="iconsVisible[5]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/meFkjAw.png"
        tooltipText="ClickUp"
        v-if="iconsVisible[6]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/9DsxTqY.png"
        tooltipText="Trello"
        v-if="iconsVisible[7]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/kpRhY1W.png"
        tooltipText="Miro"
        v-if="iconsVisible[8]"  aria-hidden="true" 
        />
        <Icon 
        imageUrl="https://i.imgur.com/rzYhM4Q.png"
        tooltipText="Firebase"
        v-if="iconsVisible[9]"  aria-hidden="true" 
        />
    </div>
  </template>
  
  <script>
  export default {
    name: "IconGroup",
    props: {
      iconsVisible: {
        type: Array,
        default: () => [false, false, false, false, false, false, false, false, false, false], // Default to all hidden
        validator: (value) => value.length === 8 && value.every((item) => typeof item === 'boolean'),
      },
    },
  };
  </script>
