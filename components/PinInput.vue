<template>
  <div>
    <div class="flex justify-center">
      <input
        v-for="(digit, index) in digits"
        :key="index"
        v-model="digits[index]"
        @input="onInput(index, $event)"
        @keydown="onKeyDown(index, $event)"
        class="w-14 text-xl font-serif text-red-600 h-14 border rounded-full text-center mx-1.5 border-red-500"
        type="text"
        maxlength="1"
      />
    </div>
    <div
      v-if="isSuccess"
      class="mt-4 text-green-500 flex justify-center font-serif text-xl border rounded-md"
    >
      Thành công
    </div>
  </div>
</template>

<script setup>
const digits = ref(["", "", "", ""]);

const onInput = (index, event) => {
  if (event.target.value.length === 1 && index < digits.value.length - 1) {
    event.target.nextElementSibling.focus();
  }
};

const onKeyDown = (index, event) => {
  if (event.key === "Backspace" && digits.value[index] === "" && index > 0) {
    event.target.previousElementSibling.focus();
  }
};
const isSuccess = computed(() => digits.value.every((digit) => digit !== ""));

// const checkSuccess = () => {
//   if (isSuccess.value) {
//     console.log("Thành công");
//   }
// };
</script>
