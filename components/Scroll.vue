<template>
  <div
    class="h-screen w-screen bg-gradient-to-l from-green-700 to-green-400 flex-col flex justify-center items-center"
  >
    <div class="text-white text-3xl mb-16">ScrollArea</div>
    <div
      class="w-64 h-72 overflow-y-scroll border border-gray-300 p-4 bg-white rounded-md"
    >
      <div class="grid grid-cols-1 gap-4">
        <div
          class="font-semibold text-xl text-red-900 bg-slate-200 p-2 rounded-md"
        >
          Tags
        </div>
        <div
          v-for="(item, index) in list"
          :key="index"
          class="bg-slate-200 rounded-md p-1 hover:bg-slate-300"
        >
          <div class="ml-2">- {{ item.name }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  list: Array,
});
</script>
