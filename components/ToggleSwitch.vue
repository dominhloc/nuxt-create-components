<template>
  <div class="flex flex-col justify-center items-center">
    <label for="toggle" class="flex items-center cursor-pointer">
      <div class="relative">
        <input
          type="checkbox"
          id="toggle"
          v-model="isChecked"
          class="sr-only peer"
        />
        <div class="block bg-slate-900 w-14 h-8 rounded-full"></div>
        <div
          class="absolute left-1 top-1 bg-slate-600 w-6 h-6 rounded-full transition peer-checked:translate-x-full peer-checked:bg-white duration-500"
        ></div>
      </div>
      <div class="ml-3 text-gray-700 text-3xl font-medium">
        {{ isChecked ? `ON` : "OFF" }}
      </div>
    </label>
  </div>
</template>

<script setup>
const isChecked = ref(false);
</script>
