<!-- Đây là cha -->

<template>
  <div class="w-full h-screen flex flex-col justify-center items-center">
    <div class="space-y-5">
      <!-- <div class="bg-blue-500">parent {{ count }} </div> -->
      <Combobox :data="data" />

      <!-- v-model:count="count" -->
      <!-- v-model:end_value="end_value" -->
      <!-- <input type="text" name="example" list="exampleList" /> -->
    </div>
  </div>
</template>

<script setup>
// const name = ref(undefined);
// const count = ref(1);
// const end_value = ref({});
const data = ref([
  {
    label: "Text A",
    value: 1,
  },
  {
    label: "Text B",
    value: 2,
  },
  {
    label: "Text C",
    value: 3,
  },
  {
    label: "Text D",
    value: 4,
  },
  {
    label: "Text E",
    value: 5,
  },
  {
    label: "Text F",
    value: 6,
  },
]);
</script>
