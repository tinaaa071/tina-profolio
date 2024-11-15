<template>
    <div class="grid grid-cols-1 gap-4 p-6 rounded-2xl border sm:gap-6 bg-B4 md:rounded-3xl border-B2 dark:bg-transparent">
      <!-- Client -->
      <div>
        <p class="mb-2">
          {{ $t('work.info.item4') }}
        </p>
        <p class="font-light">
          {{ info1 }}
        </p>
      </div>
      <!-- Service -->
      <div>
        <p class="mb-2">
          {{ $t('work.info.item5') }}
        </p>
        <ul class="font-light">
          <li v-for="(service, index) in info2" :key="index">
            {{ service }}
          </li>
        </ul>
      </div>
      <!-- Role -->
      <!-- <div>
        <p class="mb-2">
          {{ $t('work.info.item2') }}
        </p>
        <ul class="font-light">
          <li v-for="(role, index) in info3" :key="index">
            {{ role }}
          </li>
        </ul>
      </div> -->
      <!-- Team -->
      <div>
        <p class="mb-2">
          {{ $t('work.info.item6') }}
        </p>
        <!-- Members -->
        <div class="flex flex-col space-y-4">
          <div v-for="(member, index) in info4" :key="index" class="flex items-center">
            <!-- Avatar -->
            <img
              :src="member.avatarSrc"
              alt="Avatar"
              class="object-cover mr-4 w-10 h-10 rounded-full"
            />
            <!-- Member Info -->
            <div>
              <p class="text-xs font-medium opacity-50">
                {{ member.job }}
              </p>
              <p class="font-light">
                {{ member.name }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
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
        type: Array,
        required: true,
      },
      info4: {
        type: Array,
        required: true,
      }
    },
  };
  </script>
  