<template>
  <div
    class="h-screen w-screen bg-green-500 flex-col flex justify-center items-center"
  >
    <button
      @click="toggleDialog"
      class="font-serif hover:bg-green-200 h-9 flex-col flex items-center justify-center rounded-md bg-white p-4 duration-500"
    >
      Delete Account
    </button>

    <!-- Thêm thành phần con vào đây -->
    <Alert :isOpen="isOpen" @closeDialog="toggleDialog" />
  </div>
</template>

<script setup>
//
const isOpen = ref(false);
function toggleDialog() {
  isOpen.value = !isOpen.value;
  console.log("🚀 ~ toggleDialog ~ isOpen.value:", isOpen.value);
}
</script>
