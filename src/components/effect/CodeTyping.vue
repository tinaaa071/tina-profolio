<template>
    <pre ref="codeContainer" class="w-full h-32 whitespace-pre-wrap rounded-2xl sm:h-full aspect-square sm:rounded-3xl" style="margin: 0"><code ref="code" class="block overflow-hidden language-javascript" :style="{ fontSize: fontSize }">{{ displayedText }}</code></pre>
  </template>
  
  <script>
import Prism from 'prismjs';
import 'prismjs/themes/prism-tomorrow.css';
import 'prismjs/components/prism-javascript';

export default {
  data() {
    return {
      fullText: `<template>
  <div id="app">
    <h1>{{ message }}</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Hello, nice to meet you!'
    };
  }
};
<script>`,
      displayedText: '',
      currentIndex: 0,
      fontSize: '16px',
    };
  },
  mounted() {
    this.typeText();
  },
  methods: {
    typeText() {
      if (this.currentIndex < this.fullText.length) {
        this.displayedText += this.fullText[this.currentIndex];
        this.currentIndex++;
        this.$nextTick(() => {
          // Ensure the code element exists before calling Prism
          if (this.$refs.code) {
            Prism.highlightElement(this.$refs.code);
            this.scrollToBottom(); // Scroll to the bottom after updating
          }
        });
        setTimeout(this.typeText, 20); // Adjust speed here
      } else {
        setTimeout(() => {
          this.resetAnimation();
          this.typeText();
        }, 500); // Pause before restarting
      }
    },
    scrollToBottom() {
      const container = this.$refs.codeContainer;
      container.scrollTop = container.scrollHeight;
    },
    resetAnimation() {
      this.displayedText = '';
      this.currentIndex = 0;
    },
  },
};
</script>

<style>
/* Hide scrollbars for WebKit browsers (e.g., Chrome, Safari) */
pre::-webkit-scrollbar {
  display: none; /* Hide scrollbar */
}

/* Hide scrollbars for Firefox */
pre {
  scrollbar-width: none; /* Hide scrollbar */
}

/* Hide scrollbars for Edge and IE */
pre {
  -ms-overflow-style: none; /* Hide scrollbar */
}
</style>