<template>
  <div
    class="w-full h-screen bg-gradient-to-l from-green-700 to-green-400 flex flex-col items-center"
  >
    Tags Input
    <div
      class="bg-white h-fit w-2/3 p-2 flex-row flex justify-center mt-28 rounded-lg"
    >
      <form @submit.prevent="addTags()">
        <button v-for="(item, index) in data" :key="index" class="p-1.5">
          <div class="w-fit rounded-lg flex p-1.5 bg-green-400 text-white">
            {{ item.name }}
            <div class="ml-3">X</div>
          </div>
        </button>
        <input
          class="bg-slate-200 ml-1.5 w-28 p-1.5 rounded-lg"
          v-model="newtags"
          required
          placeholder="Fruits..."
        />
      </form>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  data: {
    type: Array,
    required: true,
  },
});

const data = ref([
  { id: 1, name: "Apple" },
  { id: 2, name: "Banana" },
  { id: 3, name: "Orange" },
  { id: 4, name: "Lemon" },
]);

const newtags = ref("");

function addTags() {
  console.log("🚀 ~ addTags ~ addTags:", addTags);
  let newTags = data.value.length + 1;
  console.log("🚀 ~ addTags ~ newTags:", newTags);
  data.value.push({
    id: newTags,
    name: newtags.value,
  });
  newtags.value = "";
}
//console.log("🚀 ~ addTags ~ data.value:", data.value);
</script>
