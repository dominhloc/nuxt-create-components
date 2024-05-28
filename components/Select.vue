<!-- Đây là con -->

<template>
  <div class="w-screen h-screen bg-blue-400 flex justify-center items-center">
    <div>
      <input type="text" list="dataList" class="h-9 rounded-xl w-40 px-2" />
      <datalist id="dataList">
        <option v-for="(i, index) in data" :key="index" :value="i?.lable">
          {{ i?.label }}
        </option>
      </datalist>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  data: {
    type: Array,
    default: [],
  },
});
console.log("---> asdasdasd", props.data);
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
