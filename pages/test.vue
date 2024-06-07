<template>
  <div>
    <input
      v-for="(digit, index) in digits"
      :key="index"
      v-model="digits[index]"
      class="w-12 h-12 border border-gray-300 rounded-md text-center mx-1"
      type="text"
      maxlength="1"
    />
  </div>
</template>

<script setup>
const digits = ref(["", "", "", ""]);

// const onInput = (index, event) => {
//   if (digits.value[index].length === 1 && index < digits.value.length - 1) {
//     event.target.nextElementSibling.focus();
//   }
// };
</script>
