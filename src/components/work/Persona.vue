<template>
    <div class="flex flex-col gap-3 xs:flex-row">
      <img
        :src="avatarSrc"
        alt="Avatar"
        class="object-cover w-full rounded-2xl border xs:w-1/4 border-stone-200 aspect-video"
      />
      <div class="grid grid-cols-1 gap-3 w-full xs:grid-cols-2">
        <div class="px-4 py-3 rounded-2xl border xs:col-span-2 border-stone-200">
          <span class="flex gap-2 items-center mb-3">
            <Fa6RegularUser />
            {{ $t('work.persona.item1') }}
          </span>
          <!-- u1 -->
          <ul class="leading-loose list-disc list-inside">
            <li v-for="(item, index) in items.u1" :key="index">{{ item }}</li>
          </ul>
        </div>
        <div class="px-4 py-3 rounded-2xl border border-stone-200">
          <span class="flex gap-2 items-center mb-3">
            <Fa6RegularStar />
            {{ $t('work.persona.item2') }}
          </span>
          <!-- u2 -->
          <ul class="leading-loose list-disc list-inside">
            <li v-for="(item, index) in items.u2" :key="index">{{ item }}</li>
          </ul>
        </div>
        <div class="px-4 py-3 rounded-2xl border border-stone-200">
          <span class="flex gap-2 items-center mb-3">
            <Fa6RegularLightbulb />
            {{ $t('work.persona.item3') }}
          </span>
          <!-- u3 -->
          <ul class="leading-loose list-disc list-inside">
            <li v-for="(item, index) in items.u3" :key="index">{{ item }}</li>
          </ul>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      avatarSrc: {
        type: String,
      },
      items: {
        type: Object,
        required: true,
        default: () => ({
          u1: [],
          u2: [],
          u3: [],
        }),
      },
    },
  };
  </script>
  