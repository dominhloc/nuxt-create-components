<template>
  <div class="w-screen flex-col flex justify-center items-center space-y-3">
    <div
      class="space-x-7 bg-green-800 w-96 border flex justify-center rounded-lg text-white"
    >
      <button
        v-for="(tab, index) in tabs"
        :key="index"
        class="hover:bg-green-600 w-28 h-10 rounded-lg"
        :class="{
          'bg-white text-black font-semibold': selectedIndex === index,
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
        class="space-y-1.5 w-full hover:bg-slate-200 rounded-lg h-22 p-2 text-left"
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
