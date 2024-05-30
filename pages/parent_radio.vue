<template>
  <div>
    <Radio :radiogroup="radiogroup" />
  </div>
</template>

<script setup>
const radiogroup = [
  {
    title: "Startup",
    content: "12GB/6 CPUs · 160 GB SSD disk",
  },
  {
    title: "Business",
    content: "16GB/8 CPUs · 512 GB SSD disk",
  },
  {
    title: "Enterprise",
    content: "32GB/12 CPUs · 1024 GB SSD disk",
  },
];
</script>
