<template>
  <div class="w-screen flex-col flex justify-center items-center space-y-3">
    <div
      class="space-x-7 bg-green-800 w-96 flex justify-center rounded-lg text-white"
    >
      <button
        v-for="(tab, index) in tabs"
        :key="index"
        class="hover:bg-blue-200 w-24 h-10 rounded-lg"
        :class="{
          'bg-white text-blue-500 font-semibold border-green-400 border-2':
            selectedIndex === index,
        }"
        @click="selectTab(index)"
      >
        {{ tab.title }}
      </button>
    </div>
    <div class="p-5 w-96 bg-white rounded-lg space-y-2">
      <button
        v-for="(content, index) in tabs[selectedIndex].contents"
        :key="index"
        class="space-y-1.5 w-full hover:bg-sky-100 rounded-xl h-22 p-2 text-left"
      >
        <p class="font-semibold">{{ content.content }}</p>
        <p class="text-xs text-slate-500">{{ content.comments }}</p>
      </button>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  tabs: {
    type: Array,
    required: true,
  },
});
const selectedIndex = ref(0);

function selectTab(index) {
  selectedIndex.value = index;
}
</script>
