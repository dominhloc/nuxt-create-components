<template>
  <div class="flex justify-center">
    <input
      v-for="(digit, index) in digits"
      :key="index"
      v-model="digits[index]"
      @input="onInput(index, $event)"
      @keydown="onKeyDown(index, $event)"
      class="w-12 h-12 border border-gray-300 rounded-md text-center mx-1"
      type="text"
      maxlength="1"
    />
  </div>
  <div v-if="isSuccess" class="mt-4 text-green-500">Thành công</div>
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

const checkSuccess = () => {
  if (isSuccess.value) {
    console.log("Thành công"); // Optional: Thực hiện thêm hành động khác nếu cần
  }
};
</script>
