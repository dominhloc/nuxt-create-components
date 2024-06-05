<template>
  <div class="flex flex-col justify-center items-center space-y-3">
    <div class="flex space-x-2">
      <label
        for="name"
        class="px-3 h-9 w-36 rounded-md text-white flex justify-end items-center"
        >Name</label
      >
      <input
        type="text"
        v-model="name"
        class="h-9 rounded-md flex-auto px-3 border text-white bg-gradient-to-l from-green-700 to-green-400"
      />
    </div>
    <div class="flex space-x-2">
      <label
        for="fullname"
        class="px-3 h-9 w-36 rounded-md text-white flex justify-end items-center"
        >Full Name</label
      >
      <input
        type="text"
        v-model="fullname"
        class="h-9 rounded-md flex-auto px-3 border text-white bg-gradient-to-l from-green-700 to-green-400"
      />
    </div>
    <div class="flex space-x-2">
      <label
        class="px-3 h-9 w-36 rounded-md text-white flex justify-end items-center"
        >Age</label
      >
      <input
        type="number"
        v-model="age"
        class="h-9 rounded-md flex-auto px-3 border text-white bg-gradient-to-l from-green-700 to-green-400"
      />
    </div>
  </div>
</template>

<script setup>
const name = ref("Minh Lộc");
const fullname = ref("Đỗ Minh Lộc");

const age = ref(24);
</script>
