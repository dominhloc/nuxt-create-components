<template>
  <div>
    <Dialog :dialog="dialog" />
  </div>
</template>

<script setup>
const dialog = [
  {
    title: " Edit profile",
    content: "Make changes to your profile here. Click save when you're done.",
  },
];
</script>
