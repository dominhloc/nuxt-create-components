<template>
  <div class="h-screen flex justify-center items-center">
    <div class="w-80 h-60 overflow-y-scroll border border-gray-300 p-4">
      <div class="grid grid-cols-1 gap-4">
        <!-- Nội dung mẫu -->
        <div
          v-for="(item, index) in items"
          :key="item.id"
          class="bg-gray-100 p-2 flex justify-between items-center"
        >
          <span v-if="!item.isEditing">{{ item.text }}</span>
          <input
            v-else
            v-model="item.text"
            @keyup.enter="saveEdit(item)"
            class="border p-1"
          />
          <button @click="toggleEdit(item)" class="ml-2 text-blue-500">
            {{ item.isEditing ? "Save" : "Edit" }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const items = reactive([
  { id: 1, text: "Mục 1", isEditing: false },
  { id: 2, text: "Mục 2", isEditing: false },
  { id: 3, text: "Mục 3", isEditing: false },
  { id: 4, text: "Mục 4", isEditing: false },
  { id: 5, text: "Mục 5", isEditing: false },
  // Thêm nhiều mục khác nếu cần
]);

function toggleEdit(item) {
  if (item.isEditing) {
    saveEdit(item);
  } else {
    item.isEditing = true;
  }
}

function saveEdit(item) {
  item.isEditing = false;
}
</script>
