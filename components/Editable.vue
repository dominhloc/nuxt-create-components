<template>
  <div class="w-screen flex flex-col justify-center items-center">
    <div class="border border-gray-300 p-4 rounded-md">
      <div class="flex flex-col space-y-3">
        <div
          v-for="item in list"
          :key="item.id"
          class="bg-gray-100 p-2 w-96 rounded-md flex space-x-4 font-serif justify-center items-center"
        >
          <div v-if="!item.done" class="text-slate-900 font-serif">
            {{ item.name }}
          </div>
          <input
            v-else
            v-model="item.editname"
            @keyup.enter="saveList(item)"
            class="p-1 rounded-md border"
          />
          <button
            @click="editList(item)"
            class="text-white bg-blue-500 border p-1 rounded-md hover:bg-blue-700"
          >
            {{ item.done ? "Submit" : "Edit" }}
          </button>
          <button
            v-if="item.done"
            @click="cancelEdit(item)"
            class="bg-red-500 text-white font-serif border p-1 rounded-md hover:bg-red-700"
          >
            Cancel
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  list: Array,
});

function editList(item) {
  if (item.done) {
    saveList(item);
  } else {
    item.editname = item.name;
    item.done = true;
  }
}

function saveList(item) {
  item.name = item.editname;
  item.done = false;
}

function cancelEdit(item) {
  item.editname = item.name;
  item.done = false;
}
</script>
