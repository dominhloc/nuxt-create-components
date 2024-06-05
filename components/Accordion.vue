<!-- Đây là con -->

<template>
  <div class="flex justify-center items-center">
    <div class="space-y-3 font-serif text-lg w-72 text-center">
      <button
        @click="toggleDropdown()"
        v-for="(i, index) in accordion"
        :key="index"
        class="bg-white rounded-md w-72 border-2 accordion-item"
      >
        <div
          @click="toggle(index)"
          class="accordion-header cursor-pointer p-2 text-black hover:bg-slate-300"
        >
          {{ i?.title }}
        </div>
        <div
          v-if="isOpen(index)"
          class="p-3 bg-gradient-to-l from-green-600 to-green-400 text-white border-2"
        >
          {{ i?.content }}
        </div>
      </button>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  accordion: {
    type: Array,
    required: true,
  },
});

const openIndex = ref(null);

const toggle = (index) => {
  openIndex.value = openIndex.value === index ? null : index;
};

const isOpen = (index) => {
  return openIndex.value === index;
};
</script>
