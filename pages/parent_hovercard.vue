<template>
  <div
    class="w-screen h-screen bg-gradient-to-l from-green-700 to-green-400 flex flex-col items-center"
  >
    <Hovercard :data="data" />
  </div>
</template>

<script setup>
const data = [
  {
    title: "Radix",
    user: "@radix_ui",
    content:
      "Components, icons, colors, and templates for building high-quality, accessible UI. Free and open-source.",
    comments: "0 Following - 2,900 Followers",
  },
];
</script>
