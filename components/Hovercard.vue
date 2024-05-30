<template>
  <div
    class="w-full h-screen bg-gradient-to-l from-green-700 to-green-400 flex flex-col items-center"
  >
    <button
      v-for="(item, index) in data"
      :key="index"
      class="rounded-full w-12 h-12 flex justify-center cursor-pointer transition duration-500 ease-in-out items-center bg-black mt-52 text-white"
      @mouseenter="selectHover(index)"
      @mouseleave="clearHover"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="w-7 h-7"
        viewBox="0 0 24 24"
      >
        <path
          fill="white"
          d="M11.52 24a7.68 7.68 0 0 1-7.68-7.68a7.68 7.68 0 0 1 7.68-7.68zm0-24v7.68H3.84V0zm4.8 7.68a3.84 3.84 0 1 1 0-7.68a3.84 3.84 0 0 1 0 7.68"
        />
      </svg>
    </button>
    <div
      v-if="hoveredIndex !== null"
      class="mt-2 p-3 w-3/5 bg-white rounded-lg transition duration-500 space-y-3 ease-in-out"
    >
      <h1
        class="rounded-full w-20 h-20 flex justify-center items-center ease-in-out duration-500 bg-black"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="1.2em"
          height="1.2em"
          class="w-10 h-10"
          viewBox="0 0 24 24"
        >
          <path
            fill="white"
            d="M11.52 24a7.68 7.68 0 0 1-7.68-7.68a7.68 7.68 0 0 1 7.68-7.68zm0-24v7.68H3.84V0zm4.8 7.68a3.84 3.84 0 1 1 0-7.68a3.84 3.84 0 0 1 0 7.68"
          />
        </svg>
      </h1>
      <h3 class="font-medium text-lg">{{ data[hoveredIndex].title }}</h3>
      <p class="text-gray-400">{{ data[hoveredIndex].user }}</p>
      <p class="text-gray-900">{{ data[hoveredIndex].content }}</p>
      <p class="text-sm text-gray-400">
        {{ data[hoveredIndex].comments }}
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
});

const hoveredIndex = ref(null);

function selectHover(index) {
  hoveredIndex.value = index;
}

function clearHover() {
  hoveredIndex.value = null;
}
</script>
