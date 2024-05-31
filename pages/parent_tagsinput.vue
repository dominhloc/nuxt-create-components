<template>
  <div><TagsInput :fruit="fruit" /></div>
</template>

<script setup>
import { ref } from "vue";

const fruit = ref([
  { id: 1, name: "Apple" },
  { id: 2, name: "Banana" },
  { id: 3, name: "Orange" },
  { id: 4, name: "Lemon" },
]);
</script>
