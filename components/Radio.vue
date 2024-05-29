<template>
  <div
    class="h-screen w-screen bg-blue-400 flex flex-col justify-center items-center space-y-4"
  >
    <button
      class="bg-white w-1/2 h-16 rounded-lg hover:bg-slate-200"
      v-for="(item, index) in radiogroup"
      :key="index"
      :class="id ? 'bg-red-300' : ''"
      @click="isChecked"
    >
      <div class="flex ml-4 text-sm font-bold font-serif">
        {{ item?.title }}
      </div>
      <div class="flex flex-row ml-4 text-gray-500 text-sm font-serif ">
        {{ item?.content }}
        <input
          type="checkbox"
          v-model="radiogroup.id"
          @change="getClass(item)"
          class="flex-auto"
        />
      </div>
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  radiogroup: {
    type: Array,
    default: [],
  },
});

function getClass(item) {
  if (item.id) {
    console.log("🚀 ~ getClass ~ radiogroup.id:", item.id);
    return "bg-red-500";
  }
}

const isChecked = ref(false);
console.log("🚀 ~ isChecked:", isChecked);
</script>
