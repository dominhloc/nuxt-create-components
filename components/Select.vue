<!-- Đây là con -->

<template>
  <div class="h-screen w-screen bg-blue-400 flex justify-center items-center">
    <!-- <div class="">child {{ count }}</div> -->
    <!-- <button @click="upcount">upcount</button> -->

    <!-- < <select class="border p-2 w-48 rounded-md text-left font-serif">
      <option v-for="(i, index) in data" :key="index" :value="i?.value">
        {{ i?.label }}
      </option>
    </select>  -->
    <input
      class="rounded-md pl-3 justify-center items-center"
      type="text"
      list="data"
    />
    <datalist id="data">
      <option value="Internet Explorer"></option>
      <option value="Firefox"></option>
      <option value="Chrome"></option>
      <option value="Opera"></option>
      <option value="Safari"></option>
    </datalist>
  </div>
</template>

<script setup>
// const props = defineProps({
//   data: {
//     type: Array,
//     default: [],
//   },
// });
// const end_value = defineModel("end_value");
// const count = defineModel("count");
//
// function check(item) {
//   console.log("🚀 ~ check ~ item:", item?.target?.value);
// }
// function upcount() {
//   count.value++;
//   console.log("jasdhfsdvhfjdsvh");
// }
</script>
