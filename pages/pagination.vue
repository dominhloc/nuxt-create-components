<template>
  <div
    class="h-screen w-screen bg-gradient-to-l from-green-800 to-green-600 flex justify-center items-center"
  >
    <ul class="flex space-x-1">
      <!--quay trở về trang 1 khi click -->
      <button
        class="px-4 py-2 rounded-lg text-white font-bold bg-green-700 hover:bg-green-900"
        @click="currentPage = 1"
      >
        <<
      </button>
      <!-- lùi 1 trang khi click -->
      <button
        class="px-4 py-2 rounded-lg text-white font-bold bg-green-700 hover:bg-green-900"
        :disabled="currentPage === 1"
        @click="currentPage--"
      >
        <
      </button>
      <div v-for="item in totalPages" :key="item">
        <button
          class="px-4 py-2 rounded-lg text-white font-bold hover:bg-green-500"
          :class="{ 'bg-green-800': currentPage === item }"
          @click="currentPage = item"
        >
          {{ item }}
        </button>
      </div>

      <!-- tiến 1 trang khi click -->
      <button
        class="px-4 py-2 rounded-lg text-white font-bold bg-green-700 hover:bg-green-900"
        :disabled="currentPage === totalPages"
        @click="currentPage++"
      >
        >
      </button>

      <!-- tiến đến trang cuối khi click -->
      <button
        class="px-4 py-2 rounded-lg text-white font-bold bg-green-700 hover:bg-green-900"
        @click="currentPage = totalPages"
      >
        >>
      </button>
    </ul>
  </div>
</template>

<script setup>
const currentPage = ref(1);
const totalItems = ref(100); // Tổng số mục
const itemsPerPage = ref(10); // Số mục trên mỗi trang

const totalPages = computed(() =>
  Math.ceil(totalItems.value / itemsPerPage.value)
);
</script>
