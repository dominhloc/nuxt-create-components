<template>
  <div class="w-screen flex flex-col justify-center items-center space-y-5">
    <input
      id="slider"
      type="range"
      v-model="value"
      min="0"
      max="100"
      class="w-96 h-0.5 bg-white rounded-lg cursor-pointer mt-3"
    />
    <div class="text-center font-serif text-gray-700 text-lg">
      Value: {{ value }} %
    </div>
  </div>
</template>

<script setup>
const value = ref(50);
</script>
