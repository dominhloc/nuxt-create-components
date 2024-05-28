<!-- Đây là cha -->

<template>
  <div class="w-full h-screen flex flex-col justify-center items-center">
    <div class="space-y-5">
      <!-- <div class="bg-blue-500">parent {{ count }} </div> -->
      <Accordion :accordion="accordion" />

      <!-- v-model:count="count" -->
      <!-- v-model:end_value="end_value" -->
      <!-- <input type="text" name="example" list="exampleList" /> -->
    </div>
  </div>
</template>

<script setup>
const accordion = [
  {
    id: "item-1",
    title: "Is it accessible?",
    content: "Yes. It adheres to the WAI-ARIA design pattern.",
  },
  {
    id: "item-2",
    title: "Is it unstyled?",
    content:
      "Yes. It's unstyled by default, giving you freedom over the look and feel.",
  },
  {
    id: "item-3",
    title: "Can it be animated?",
    content: "Yes! You can use the transition prop to configure the animation.",
  },
];
</script>
