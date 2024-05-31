<template>
  <div>
    <Editable :list="list" />
  </div>
</template>

<script setup>
const list = ref([
  { id: 1, name: "Nội Dung 1", done: false, editname: "Nội Dung 1" },
  { id: 2, name: "Nội Dung 2", done: false, editname: "Nội Dung 2" },
  { id: 3, name: "Nội Dung 3", done: false, editname: "Nội Dung 3" },
]);
</script>
