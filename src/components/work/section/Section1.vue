<!-- Info -->
<template>
    <Section class="px-6 xl:px-56 md:p-8">
      <div class="grid gap-6 w-full xl:grid-cols-10 xl:gap-10 xs:grid-cols-8">
        <!-- Left -->
        <InfoCard
          class="xs:col-span-3 h-fit"
          :info1="info1"
          :info2="info2"
          :info3="info3"
          :info4="info4"
        />
        <!-- Right -->
        <div class="xl:col-span-7 xs:col-span-5">
          <p class="mb-6 font-normal text-justify" v-html="content">
          </p>
          <CardTilt v-if="bannerSrc">
            <img 
              :src="bannerSrc"
              alt="Avatar"
              class="object-cover w-full rounded-2xl xl:rounded-3xl aspect-video"
            >
          </CardTilt>
          <Parallax
            v-if="bgImg"
            :backgroundImage="bgImg"
            speed="0.08"
            customClass="rounded-2xl xl:rounded-3xl aspect-video w-full"
          />
          <div class="mt-4">
            <slot></slot>
          </div>
        </div>
      </div>
    </Section>
  </template>
  
  <script>
  export default {
    props: {
      info1: {
        type: String,
        required: true,
      },
      info2: {
        type: Array,
        required: true,
      },
      info3: {
        type: String,
        required: true,
      },
      info4: {
        type: Array,
        required: true,
      },
      content: {
        type: String,
        required: true,
      },
      bannerSrc: {
        type: String,
        default: '',
      },
      bgImg: {
        type: String,
        default: '',
      },
    },
  };
  </script>
  