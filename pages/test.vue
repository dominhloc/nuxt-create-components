<template>
  <div :class="`aspect-w-${width} aspect-h-${height}`">
    <slot></slot>
  </div>
</template>

<script setup>

const props = defineProps({
  width: {
    type: Number,
    required: true,
  },
  height: {
    type: Number,
    required: true,
  },
});
</script>


