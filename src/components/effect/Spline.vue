<template>
  <div class="">
    <iframe
      :src="splineUrl"
      frameborder="0"
      allowfullscreen
      loading="lazy"
      class="w-full h-[500px] rounded-3xl" 
    ></iframe>
  </div>
</template>

<script setup>
const splineUrl = 'https://my.spline.design/forestphysicscopycopy-2ba27a184a076911619f0ea1d8cfa268/'; 
</script>