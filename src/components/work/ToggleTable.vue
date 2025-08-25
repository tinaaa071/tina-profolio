<template>
    <div class="flex flex-col gap-4">
        <button @click="toggleTable" class="p-2 text-sm border-2 rounded-lg w-fit dark:text-white border-stone-500 dark:border-B3 h-fit whitespace-nowrap text-stone-500">
        {{ showFirstTable ? $t('project1.data.btn-2') : $t('project1.data.btn-1') }}
        </button>
  
   <div v-if="showFirstTable" class="w-full mx-auto overflow-hidden border border-gray-200 rounded-2xl">
    <table class="w-full text-sm text-gray-900 bg-white">
    <thead class="text-center bg-gray-100">
        <tr>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-1') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-2') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-3') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-4') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-7') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-8') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-9') }}</th>
        </tr>
    </thead>
    <tbody>
        <tr class="text-center">
        <td class="px-4 py-2">{{ $t('project1.data.tc-1') }}</td>
        <td class="px-4 py-2"><code class="bg-gray-100">view_course_detail</code></td>
        <td class="px-4 py-2">72</td>
        <td class="px-4 py-2">72</td>
        <td class="px-4 py-2">0</td>
        <td class="px-4 py-2">-</td>
        <td class="px-4 py-2">100%</td>
        </tr>
        <tr class="text-center bg-gray-50">
        <td class="px-4 py-2">{{ $t('project1.data.tc-2') }}</td>
        <td class="px-4 py-2"><code class="bg-gray-100">click_register_button</code></td>
        <td class="px-4 py-2">69</td>
        <td class="px-4 py-2">69</td>
        <td class="px-4 py-2">0</td>
        <td class="px-4 py-2">3</td>
        <td class="px-4 py-2">95.8%</td>
        </tr>
        <tr class="text-center ">
        <td class="px-4 py-2">{{ $t('project1.data.tc-3') }}</td>
        <td class="px-4 py-2"><code class="bg-gray-100">confirm_registration</code></td>
        <td class="px-4 py-2">69</td>
        <td class="px-4 py-2">69</td>
        <td class="px-4 py-2">0</td>
        <td class="px-4 py-2">0</td>
        <td class="px-4 py-2">95.8%</td>
        </tr>
        <tr class="text-center bg-red-100">
        <td class="px-4 py-2">{{ $t('project1.data.tc-4') }}</td>
        <td class="px-4 py-2"><code class="bg-gray-100">fill_registration_form</code></td>
        <td class="px-4 py-2">65</td>
        <td class="px-4 py-2 text-red-500">41</td>
        <td class="px-4 py-2 text-red-500">24</td>
        <td class="px-4 py-2 text-red-500">4</td>
        <td class="px-4 py-2 text-red-500">56.9%</td>
        </tr>
        <tr class="text-center ">
        <td class="px-4 py-2">{{ $t('project1.data.tc-5') }}</td>
        <td class="px-4 py-2"><code class="bg-gray-100">submit_registration</code></td>
        <td class="px-4 py-2">41</td>
        <td class="px-4 py-2">35</td>
        <td class="px-4 py-2">6</td>
        <td class="px-4 py-2">24</td>
        <td class="px-4 py-2">48.6%</td>
        </tr>
        <tr class="text-center bg-gray-50">
        <td class="px-4 py-2">{{ $t('project1.data.tc-6') }}</td>
        <td class="px-4 py-2"><code class="bg-gray-100">registration_success</code></td>
        <td class="px-4 py-2">35</td>
        <td class="px-4 py-2">35</td>
        <td class="px-4 py-2">0</td>
        <td class="px-4 py-2">6</td>
        <td class="px-4 py-2">48.6%</td>
        </tr>
    </tbody>
    </table>
  </div>
  <div v-else class="w-full mx-auto overflow-hidden border border-gray-200 rounded-2xl">
    <table class="w-full text-sm text-gray-900 bg-white">
      <thead class="text-center bg-gray-100">
        <tr>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-1') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-2') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-3') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-4') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-7') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-8') }}</th>
        <th class="px-4 py-2 text-center">{{ $t('project1.data.th-9') }}</th>
        </tr>
      </thead>
      <tbody>
        <tr class="text-center">
          <td class="px-4 py-2">{{ $t('project1.data.tc-1') }}</td>
          <td class="px-4 py-2"><code class="bg-gray-100">view_course_detail</code></td>
          <td class="px-4 py-2">72</td>
          <td class="px-4 py-2">72</td>
          <td class="px-4 py-2">0</td>
          <td class="px-4 py-2">-</td>
          <td class="px-4 py-2">100%</td>
        </tr>
        <tr class="text-center">
          <td class="px-4 py-2">{{ $t('project1.data.tc-2') }}</td>
          <td class="px-4 py-2"><code class="bg-gray-100">click_register_button</code></td>
          <td class="px-4 py-2">69</td>
          <td class="px-4 py-2">69</td>
          <td class="px-4 py-2">0</td>
          <td class="px-4 py-2">3</td>
          <td class="px-4 py-2">95.8%</td>
        </tr>
        <tr class="text-center">
          <td class="px-4 py-2">{{ $t('project1.data.tc-3') }}</td>
          <td class="px-4 py-2"><code class="bg-gray-100">confirm_registration</code></td>
          <td class="px-4 py-2">69</td>
          <td class="px-4 py-2">69</td>
          <td class="px-4 py-2">0</td>
          <td class="px-4 py-2">0</td>
          <td class="px-4 py-2">95.8%</td>
        </tr>
        <tr class="text-center bg-green-100">
          <td class="px-4 py-2">{{ $t('project1.data.tc-3-1') }}</td>
          <td class="px-4 py-2"><code class="bg-gray-100">fill_personal_info</code></td>
          <td class="px-4 py-2">65</td>
          <td class="px-4 py-2">57</td>
          <td class="px-4 py-2">8</td>
          <td class="px-4 py-2">4</td>
          <td class="px-4 py-2">79.2%</td>
        </tr>
        <tr class="text-center bg-green-100">
          <td class="px-4 py-2">{{ $t('project1.data.tc-3-2') }}</td>
          <td class="px-4 py-2"><code class="bg-gray-100">fill_upload_documents</code></td>
          <td class="px-4 py-2">57</td>
          <td class="px-4 py-2">55</td>
          <td class="px-4 py-2">2</td>
          <td class="px-4 py-2">0</td>
          <td class="px-4 py-2">76.4%</td>
        </tr>
        <tr class="text-center bg-green-100">
          <td class="px-4 py-2">{{ $t('project1.data.tc-5') }}</td>
          <td class="px-4 py-2"><code class="bg-gray-100">submit_registration</code></td>
          <td class="px-4 py-2">55</td>
          <td class="px-4 py-2">54</td>
          <td class="px-4 py-2">1</td>
          <td class="px-4 py-2">0</td>
          <td class="px-4 py-2">75%</td>
        </tr>
        <tr class="text-center">
          <td class="px-4 py-2">{{ $t('project1.data.tc-6') }}</td>
          <td class="px-4 py-2"><code class="bg-gray-100">registration_success</code></td>
          <td class="px-4 py-2">55</td>
          <td class="px-4 py-2">54</td>
          <td class="px-4 py-2">0</td>
          <td class="px-4 py-2">0</td>
          <td class="px-4 py-2">75%</td>
        </tr>
      </tbody>
    </table>
  </div>
    </div>
  </template>
  
  <style>
    .slidev-layout th {
        text-align: center;
    }
  </style>

  <script>
  export default {
    data() {
      return {
        showFirstTable: true,  // 控制目前顯示哪個表格
      };
    },
    methods: {
      toggleTable() {
        this.showFirstTable = !this.showFirstTable;
      },
    },
  };
  </script>
  