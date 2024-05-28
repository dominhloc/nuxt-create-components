<!-- Đây là cha -->

<template>
  <!-- <div class="w-full h-screen flex flex-col justify-center items-center"> -->
  <!-- <div class="space-y-5"> -->
  <!-- <div class="bg-blue-500">parent {{ count }} </div> -->
  <Select :data="data" />

  <!-- v-model:count="count" -->
  <!-- v-model:end_value="end_value" -->
  <!-- <input type="text" name="example" list="exampleList" /> -->
  <!-- </div> -->
  <!-- </div> -->
</template>

<script setup>
// const name = ref(undefined);
// const count = ref(1);
// const end_value = ref({});
const data = ref([
  {
    label: "Audi",
    value: 1,
  },
  {
    label: "BMW",
    value: 2,
  },
  {
    label: "Ford",
    value: 3,
  },
  {
    label: "Honda",
    value: 4,
  },
  {
    label: "Mer",
    value: 5,
  },
  {
    label: "Mazda",
    value: 6,
  },
]);
</script>
