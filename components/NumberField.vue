<template>
  <div class="space-y-3">
    <div class="flex text-white justify-center items-center text-xl font-serif">
      Age
    </div>
    <div class="flex justify-center items-center space-x-3">
      <button
        @click="reduceQuantity"
        class="flex justify-center rounded-lg hover:bg-slate-300 border items-center w-7 h-7"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="1.2em"
          height="1.2em"
          viewBox="0 0 24 24"
        >
          <path fill="white" d="M19 12.998H5v-2h14z" />
        </svg>
      </button>
      <input
        id="quantity"
        v-model="quantity"
        class="border w-96 text-center font-semibold rounded p-1 pl-4 pr-4 quantity-input"
        @input="validateQuantity"
      />
      <button
        @click="increaseQuantity"
        class="flex justify-center rounded-lg hover:bg-slate-300 border font-semibold items-center w-7 h-7"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="1.2em"
          height="1.2em"
          viewBox="0 0 24 24"
        >
          <path fill="white" d="M11 13H5v-2h6V5h2v6h6v2h-6v6h-2z" />
        </svg>
      </button>
    </div>
  </div>
</template>

<script setup>
const quantity = ref(18);

const increaseQuantity = () => {
  quantity.value++;
};

const reduceQuantity = () => {
  if (quantity.value > 0) {
    quantity.value--;
  }
};

const validateQuantity = () => {
  if (quantity.value < 0) {
    quantity.value = 0;
  }
};
</script>
