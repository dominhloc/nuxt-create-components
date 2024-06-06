<template>
  <div>
    <div class="p-3 flex justify-center items-center">
      <button
        @click="handleClick"
        class="p-2 w-96 rounded-md border hover:bg-green-600 text-white font-semibold font-mono"
      >
        Hiển Thị Tin Nhắn
      </button>
    </div>
    <div
      v-if="isShow"
      class="fixed bottom-4 right-4 p-3 rounded shadow-lg border transition duration-300 bg-white text-black"
    >
      <div class="flex flex-col items-center justify-between w-fit">
        <div class="space-y-1.5">
          <div class="font-semibold">Tin Nhắn Mới</div>
          <div class="text-sm text-slate-600 ml-2">
            - Nội dung tin nhắn mới 1-2-3-4-5-6-7-8-9
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const isShow = ref(false);
const timerRef = ref(0);

const handleClick = () => {
  isShow.value = false;
  setTimeout(() => {
    isShow.value = true;
    timerRef.value = window.setTimeout(() => {
      isShow.value = false;
    }, 2500);
  }, 300);
};
</script>
