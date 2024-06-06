<template>
  <div class="w-screen flex flex-col justify-center items-center space-y-4">
    <div
      class="border bg-slate-100 w-96 h-16 rounded-lg cursor-pointer flex flex-col justify-center px-4 space-y-2"
      v-for="(item, index) in radiogroup"
      :key="index"
      :class="{
        'bg-blue-300': selectedIndex === index,
      }"
      @click="selectItem(index)"
    >
      <div class="flex flex-row">
        <div>
          <div class="text-sm font-bold font-serif">
            {{ item?.title }}
          </div>
          <div class="ml-2 mt-1 items-center text-gray-500 text-sm font-serif">
            {{ item?.content }}
            <div class="flex-auto flex justify-end items-center"></div>
          </div>
        </div>
        <div class="flex flex-auto justify-end items-center">
          <input
            v-if="selectedIndex === index"
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
