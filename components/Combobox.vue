<template>
  <div class="h-36 flex flex-col justify-center items-center">
    <div class="relative">
      <input
        type="text"
        placeholder=" Placeholder... "
        class="h-10 rounded-md w-96 px-2 font-semibold text-sm"
        v-model="searchQuery"
        @focus="showDropdown = true"
        @blur="hideDropdown"
        @input="filterOptions"
      />
      <div
        v-if="showDropdown"
        class="absolute bg-white border w-full font-semibold rounded-md"
      >
        <div
          v-for="(option, index) in filteredOptions"
          :key="index"
          class="p-2 hover:bg-gray-200 cursor-pointer rounded-md border"
          @mousedown="selectOption(option.label)"
        >
          {{ option.label }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  data: {
    type: Array,
    default: [],
  },
});

const searchQuery = ref("");
const showDropdown = ref(false);
const filteredOptions = ref(props.data);

const filterOptions = () => {
  if (searchQuery.value) {
    filteredOptions.value = props.data.filter((option) =>
      option.label.toLowerCase().includes(searchQuery.value.toLowerCase())
    );
  } else {
    filteredOptions.value = props.data;
  }
};

const selectOption = (label) => {
  searchQuery.value = label;
  showDropdown.value = false;
};

const hideDropdown = () => {
  setTimeout(() => {
    showDropdown.value = false;
  }, 200);
};
</script>
