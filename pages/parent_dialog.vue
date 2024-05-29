<template>
  <div
    class="h-screen w-screen bg-slate-600 flex-col flex justify-center items-center"
  >
    <button
      @click="toggleDialog"
      class="font-serif hover:bg-slate-300 h-9 flex-col flex items-center justify-center rounded-md bg-white p-4 duration-500"
    >
      Edit profile
    </button>

    <!-- Thêm thành phần con vào đây -->
    <Dialog :isOpen="isOpen" @closeDialog="toggleDialog" />
  </div>
</template>

<script setup>
const isOpen = ref(false);

const toggleDialog = () => {
  isOpen.value = !isOpen.value;
};
</script>

<style></style>
