<template>
  <div v-if="isOpen">
    <div
      class="fixed -translate-x-1/2 -translate-y-1/2 rounded-md space-y-3 bg-white p-3 shadow-lg"
    >
      <div
        class="text-black text-2xl w-5/5 text-center font-serif bg-slate-300 rounded-md"
      >
        Are you absolutely sure?
      </div>
      <p class="text-gray-500 text-sm">
        This action cannot be undone. This will permanently delete your account
        and remove your data from our servers.
      </p>
      <div class="space-y-3">
        <form @submit.prevent="saveChanges" class="flex flex-row space-x-4">
          <button
            type="submit"
            @click="handleAction"
            class="flex-1 h-9 rounded-md bg-red-200 text-red-700 px-5 font-serif border hover:bg-red-300 duration-300"
          >
            Yes, delete account
          </button>

          <button
            @click="closeDialog"
            class="h-9 w-24 border bg-blue-200 rounded-md hover:bg-slate-300 font-serif"
          >
            Cancel
          </button>
        </form>
        <div
          v-if="isAction"
          class="bg-slate-300 text-center rounded-md font-serif"
        >
          Deleted Successfully
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  isOpen: {
    type: Boolean,
  },
});

const emits = defineEmits(["closeDialog"]);

function closeDialog() {
  emits("closeDialog");
}

const isAction = ref(false);
function handleAction(params) {
  isAction.value = !isAction.value;
  console.log("🚀 ~ handleAction ~ isAction.value:", isAction.value);
}
</script>
