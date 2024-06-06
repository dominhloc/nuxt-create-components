<template>
  <div class="flex flex-col justify-center items-center">
    <button
      v-if="isButtonVisible"
      @click="toggleDialog"
      class="font-serif hover:bg-slate-300 h-9 w-44 flex-col flex items-center justify-center rounded-md bg-white p-4 duration-500"
    >
      Edit profile
    </button>
    <div v-if="isOpen">
      <div
        v-for="(item, index) in dialog"
        :key="index"
        class="bg-white p-6 w-96 rounded-md space-y-5"
      >
        <div class="flex flex-row items-center">
          <div class="text-2xl font-semibold flex-1">
            {{ item?.title }}
          </div>
          <div class="flex justify-end">
            <button
              @click="closeDialog"
              class="flex h-7 w-7 items-center justify-center rounded-full hover:bg-slate-300"
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
        <div class="text-gray-600">{{ item?.content }}</div>
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

        <form
          @submit.prevent="saveChanges"
          class="flex flex-row space-x-4 justify-center"
        >
          <button
            @click="handleAction()"
            class="h-9 rounded-md px-5 font-serif border hover:bg-slate-300 duration-300"
          >
            Save changes
          </button>
        </form>
      </div>
    </div>
    <div
      v-if="isSave"
      class="p-3 border bg-red-500 rounded-lg text-white font-semibold font-serif"
    >
      Saved Successfully
    </div>
  </div>
</template>

<script setup>
const dialog = defineModel("dialog", {
  type: Array,
  required: true,
});

const isOpen = ref(false);
const isButtonVisible = ref(true);
const isSave = ref(false);

const name = ref("Minh Lộc");
const username = ref("@minhloc.do");

const toggleDialog = () => {
  isOpen.value = !isOpen.value;
  isButtonVisible.value = false;
  //console.log("🚀 ~ toggleDialog ~ isOpen.value:", isOpen.value);
};

const closeDialog = () => {
  isOpen.value = false;
  isButtonVisible.value = true;
};

const handleAction = () => {
  isSave.value = true;
  console.log("🚀 ~ handleAction ~ isSave.value:", isSave.value);
  isOpen.value = false;
  isButtonVisible.value = false;
};
</script>
