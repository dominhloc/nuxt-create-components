<template>
  <div class="flex flex-col justify-center items-center space-y-5">
    <button
      v-if="isButtonVisible"
      @click="toggleAlert"
      class="bg-white w-44 text-green-800 font-serif p-2 rounded-lg hover:bg-green-200 h-9 flex-col flex items-center justify-center duration-500"
    >
      Delete Account
    </button>
    <div
      v-if="isOpen"
      class="flex justify-center items-center bg-white p-4 h-fit w-96 rounded-lg"
    >
      <div v-for="(item, index) in alert" :key="index" class="space-y-5">
        <div class="text-xl font-semibold">{{ item?.title }}</div>
        <div class="text-sm text-gray-600">{{ item?.content }}</div>
        <div class="space-y-3">
          <form @submit.prevent="saveChanges" class="flex flex-row space-x-4">
            <button
              @click="handleAction()"
              class="flex-1 h-9 rounded-md bg-red-200 text-red-700 px-5 font-serif border hover:bg-red-300 duration-300"
            >
              Yes, delete account
            </button>

            <button
              @click="closeAlert"
              class="h-9 w-24 border bg-blue-200 rounded-md hover:bg-slate-300 font-serif"
            >
              Cancel
            </button>
          </form>
        </div>
      </div>
    </div>
    <div
      v-if="isDeleted"
      class="bg-white p-3 rounded-lg text-green-900 font-serif"
    >
      Deleted Successfully
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  alert: {
    type: Array,
    required: true,
  },
});

const isOpen = ref(false);
const isButtonVisible = ref(true);
const isDeleted = ref(false);

const toggleAlert = () => {
  isOpen.value = !isOpen.value;
  isButtonVisible.value = false;
  //console.log("🚀 ~ toggleAlert ~ isOpen.value:", isOpen.value);
};

const closeAlert = () => {
  isOpen.value = false;
  isButtonVisible.value = true;
};

const handleAction = () => {
  isDeleted.value = true;
  console.log("🚀 ~ handleAction ~ isDeleted.value:", isDeleted.value);
  isOpen.value = false;
  isButtonVisible.value = false;
};
</script>
