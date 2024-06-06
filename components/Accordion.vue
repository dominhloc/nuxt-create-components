<!-- Đây là con -->

<template>
  <div class="flex justify-center items-center">
    <div class="space-y-3 font-serif text-lg text-center">
      <button
        @click="toggleDropdown()"
        v-for="(i, index) in accordion"
        :key="index"
        class="rounded-md w-96 border accordion-item"
      >
        <div
          @click="toggle(index)"
          class="accordion-header cursor-pointer p-2 text-black hover:bg-blue-100"
        >
          {{ i?.title }}
        </div>
        <div
          v-if="isOpen(index)"
          class="p-3 bg-white text-black border-2 rounded-md"
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
