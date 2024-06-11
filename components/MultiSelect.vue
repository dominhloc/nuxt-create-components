<template>
  <div class="h-36 flex flex-col justify-center items-center">
    <div class="relative">
      <input
        type="text"
        placeholder="Select..."
        class="h-10 rounded-md w-96 px-2 border border-black font-semibold text-sm text-center"
        v-model="displayText"
        @focus="showDropdown = true"
        @blur="hideDropdown"
        @input="filterOptions"
      />
      <div
        v-if="showDropdown"
        class="absolute bg-white w-full font-semibold rounded-md mt-1 z-10 overflow-x-auto"
      >
        <div
          v-for="(option, index) in filteredOptions"
          :key="index"
          class="flex items-center p-2 hover:bg-gray-300 cursor-pointer rounded-md border"
          @mousedown.prevent="toggleOption(option.label)"
        >
          <input
            type="checkbox"
            :checked="isSelected(option.label)"
            class="mr-2 rounded-md bg-slate-500"
          />
          <button>{{ option.label }}</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  data: {
    type: Array,
    default: () => [],
  },
});

const searchQuery = ref("");
const showDropdown = ref(false);
const filteredOptions = ref(props.data);
const selectedOptions = ref([]);
const displayText = ref("");

const filterOptions = () => {
  if (searchQuery.value) {
    filteredOptions.value = props.data.filter((option) =>
      option.label.toLowerCase().includes(searchQuery.value.toLowerCase())
    );
  } else {
    filteredOptions.value = props.data;
  }
};

const toggleOption = (label) => {
  if (isSelected(label)) {
    selectedOptions.value = selectedOptions.value.filter(
      (option) => option !== label
    );
  } else {
    selectedOptions.value.push(label);
  }
  updateDisplayText();
};

const isSelected = (label) => {
  return selectedOptions.value.includes(label);
};

const updateDisplayText = () => {
  displayText.value = selectedOptions.value.join(" , ");
};

const hideDropdown = () => {
  setTimeout(() => {
    showDropdown.value = false;
  }, 200);
};
</script>
