<template>
  <div>
    <img :src="src" :alt="alt" class="w-16 h-16 rounded-full object-cover border" />
  </div>
</template>

<script setup>
const props = defineProps({
  src: {
    type: String,
    required: true,
  },
  alt: {
    type: String,
    default: "Avatar",
  },
});
</script>
