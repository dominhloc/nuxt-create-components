<!-- Đây là cha -->

<template>
  <div class="w-full h-screen flex flex-col justify-center items-center">
    <div class="space-y-5">
      <Combobox :data="data" />
    </div>
  </div>
</template>

<script setup>
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
