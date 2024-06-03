<template>
  <div class="h- w-screen flex flex-col justify-center items-center space-y-10">
    <input
      id="slider"
      type="range"
      v-model="value"
      min="0"
      max="100"
      class="w-2/3 h-0.5 bg-white rounded-lg cursor-pointer"
    />
    <div class="text-center font-serif text-gray-700 text-lg">
      Value: {{ value }} %
    </div>
  </div>
</template>

<script setup>
const value = ref(50);
</script>
