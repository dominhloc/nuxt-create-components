<template>
  <div>
    <Alert :alert="alert" />
  </div>
</template>

<script setup>
const alert = [
  {
    title: " Are you absolutely sure?",
    content:
      "This action cannot be undone. This will permanently delete your account and remove your data from our servers.",
  },
];
</script>

