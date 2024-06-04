<template>
  <div class="w-screen flex-col flex justify-center items-center space-y-4">
    <div
      class="flex justify-center bg-green-700 text-white items-center space-x-4 w-80 rounded-lg"
    >
      <button
        v-for="(item, index) in tabs1"
        :key="index"
        class="hover:bg-slate-200 w-24 h-10 flex justify-center items-center rounded-lg"
        :class="{
          'bg-white text-blue-500 font-semibold border-green-400 border-2':
            selectedIndex === index,
        }"
        @mouseenter="selectTab(index)"
      >
        {{ item?.title }}
      </button>
    </div>
    <div class="p-5 w-96 bg-white rounded-lg space-y-4">
      <button
        v-for="(content, index) in tabs1[selectedIndex].contents"
        :key="index"
        class="space-y-1.5 w-full hover:bg-sky-100 rounded-xl h-22 p-2 text-left"
      >
        <p class="text-lg font-semibold">{{ content.content }}</p>
        <p class="text-sm text-slate-500">{{ content.comments }}</p>
      </button>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  tabs1: {
    type: Array,
    required: true,
  },
});

const selectedIndex = ref(0);

function selectTab(index) {
  selectedIndex.value = index;
}
</script>
