<template>
  <div class="w-full flex justify-center">
    <div class="bg-white w-96 p-1 flex flex-wrap space-x-3 rounded-lg">
      <div
        v-for="item in fruit"
        :key="item.id"
        class="flex justify-center items-center space-x-1 bg-pink-600 p-1 rounded-md text-white h-fit w-fit ml-3 mt-1.5 mb-1.5"
      >
        <span>{{ item.name }}</span>
        <button
          @click="removeFruit(item.id)"
          class="h-5 flex justify-center items-center rounded-md hover:bg-green-300 w-5"
        >
          X
        </button>
      </div>
      <input
        v-model="newFruit"
        @keyup.enter="addFruit"
        placeholder="Fruits..."
        class="mt-2 ml-3 w-16 mb-1.5 p-1 rounded-md"
      />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  fruit: Array,
});

const newFruit = ref("");

function addFruit() {
  //console.log("🚀 ~ addFruit ~ addFruit:", addFruit);
  const nextId = ref(props.fruit.length + 1);
  props.fruit.push({ id: nextId.value, name: newFruit.value });
  //console.log("🚀 ~ addFruit ~ nextId.value:", nextId.value);
  newFruit.value = "";
}

function removeFruit(id) {
  const x = props.fruit.findIndex((item) => item.id === id);
  //console.log("🚀 ~ removeFruit ~ x:", x);
  if (x !== -1) {
    props.fruit.splice(x, 1);
  }
}
</script>
