<template>
  <div
    class="h-screen w-screen bg-gradient-to-l from-green-700 to-green-400 flex flex-col justify-center items-center space-y-10"
  >
    <label for="slider" class="text-white font-serif text-3xl">Slider</label>
    <input
      id="slider"
      type="range"
      v-model="value"
      min="0"
      max="100"
      class="w-2/3 h-0.5 bg-white rounded-lg cursor-pointer"
    />
    <div class="text-center font-serif text-white text-lg">
      Value: {{ value }} %
    </div>
  </div>
</template>

<script setup>
const value = ref(50);
</script>
