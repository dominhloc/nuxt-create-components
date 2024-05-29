<template>
  <div v-if="isOpen">
    <div
      class="fixed -translate-x-1/2 -translate-y-1/2 rounded-md space-y-5 bg-white p-8 shadow-lg"
    >
      <div
        class="text-black text-2xl w-32 text-center font-serif bg-slate-300 rounded-md"
      >
        Edit profile
      </div>
      <p class="text-gray-500">
        Make changes to your profile here. Click save when you're done.
      </p>
      <form @submit.prevent="saveChanges" class="space-y-3">
        <div class="flex flex-row items-center justify-center space-x-5">
          <label
            for="name"
            class="px-3 h-9 w-20 rounded-md text-center flex justify-center items-center border"
            >Name</label
          >
          <input
            type="text"
            id="name"
            v-model="name"
            class="h-9 rounded-md flex-auto px-3 border"
          />
        </div>
        <div class="flex flex-row items-center justify-center space-x-5">
          <label
            for="username"
            class="px-3 h-9 w-20 rounded-md text-center flex justify-center items-center border"
            >Username</label
          >
          <input
            type="text"
            id="username"
            v-model="username"
            class="h-9 rounded-md flex-auto px-3 border"
          />
        </div>
        <div class="flex justify-end">
          <button
            type="submit"
            class="h-9 items-center justify-center rounded-md px-5 font-serif border hover:bg-slate-300 duration-300"
          >
            Save changes
          </button>
        </div>
      </form>
      <button
        @click="closeDialog"
        class="absolute top-0 right-4 flex h-7 w-7 items-center justify-center rounded-full hover:bg-slate-300"
        aria-label="Close"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="1.2em"
          height="1.2em"
          class="w-20 h-20"
          viewBox="0 0 24 24"
        >
          <path
            fill="black"
            d="M12 4c-4.419 0-8 3.582-8 8s3.581 8 8 8s8-3.582 8-8s-3.581-8-8-8m3.707 10.293a.999.999 0 1 1-1.414 1.414L12 13.414l-2.293 2.293a.997.997 0 0 1-1.414 0a.999.999 0 0 1 0-1.414L10.586 12L8.293 9.707a.999.999 0 1 1 1.414-1.414L12 10.586l2.293-2.293a.999.999 0 1 1 1.414 1.414L13.414 12z"
          />
        </svg>
      </button>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  isOpen: {
    type: Boolean,
  },
});

const name = ref("Minh Lộc");
const username = ref("@minhloc.do");

const emits = defineEmits(["closeDialog"]);
function closeDialog() {
  emits("closeDialog");
}
</script>
