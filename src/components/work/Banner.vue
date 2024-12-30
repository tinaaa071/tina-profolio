<template>
  <!-- bg -->
  <div
    class="sm:bg-fixed top-0 left-0 w-full sm:h-[560px] h-[480px] bg-cover bg-bottom"
    :style="{ backgroundImage: `url(${bannerSrc})` }"
  >
  </div>
</template>
  
  <script>
  export default {
    props: {
      bannerSrc: {
        type: String,
        default: '',
      }
    },
  };
  </script>
  