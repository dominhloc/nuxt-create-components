<template>
  <div class="flex flex-col items-center mt-5">
    <div>
      <MultiSelect :data="data" />
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
  {
    label: "Text G",
    value: 7,
  },
  {
    label: "Text H",
    value: 8,
  },
  {
    label: "Text K",
    value: 9,
  },
]);
</script>
