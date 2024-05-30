<template>
  <div
    class="h-screen w-screen bg-blue-400 flex flex-col justify-center items-center space-y-4"
  >
    <div
      class="bg-white w-1/2 h-16 rounded-lg cursor-pointer flex flex-col justify-center px-4 space-y-2 hover:bg-slate-200"
      v-for="(item, index) in radiogroup"
      :key="index"
      @click="selectItem(index)"
    >
      <div class="flex ml-4 text-sm font-bold font-serif">
        {{ item?.title }}
      </div>
      <div class="flex flex-row ml-4 text-gray-500 text-sm font-serif">
        {{ item?.content }}
        <div class="flex-auto flex justify-end items-center">
          <input
            type="checkbox"
            :checked="selectedIndex === index"
            @change.stop="selectItem(index)"
            class="h-4 w-4"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  radiogroup: {
    type: Array,
    default: () => [],
  },
});
const selectedIndex = ref(null);

function selectItem(index) {
  if (selectedIndex.value === index) {
    selectedIndex.value = null;
  } else {
    selectedIndex.value = index;
  }
}
</script>
