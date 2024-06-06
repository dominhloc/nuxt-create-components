<template>
  <div class="w-screen flex flex-col justify-center items-center space-y-4">
    <div
      class="border bg-slate-100 w-1/2 h-16 rounded-lg cursor-pointer flex flex-col justify-center px-4 space-y-2"
      v-for="(item, index) in radiogroup"
      :key="index"
      :class="{
        'bg-blue-300': selectedIndex === index,
      }"
      @click="selectItem(index)"
    >
      <div class="flex flex-row">
        <div>
          <div class="text-sm font-bold font-serif">
            {{ item?.title }}
          </div>
          <div class="ml-2 mt-1 items-center text-gray-500 text-sm font-serif">
            {{ item?.content }}
            <div class="flex-auto flex justify-end items-center"></div>
          </div>
        </div>
        <div class="flex flex-auto justify-end items-center">
          <input
            v-if="selectedIndex === index"
            type="checkbox"
            :checked="selectedIndex === index"
            @change.stop="selectItem(index)"
            class="hidden peer"
          />
          <div
            v-if="selectedIndex === index"
            class="w-6 h-6 flex justify-center items-center"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="1.2em"
              height="1.2em"
              viewBox="0 0 48 48"
            >
              <circle cx="24" cy="24" r="21" fill="#623c3c" />
              <path
                fill="black"
                d="M34.6 14.6L21 28.2l-5.6-5.6l-2.8 2.8l8.4 8.4l16.4-16.4z"
              />
            </svg>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const radiogroup = [
  {
    title: "Startup",
    content: "12GB/6 CPUs · 160 GB SSD disk",
  },
  {
    title: "Business",
    content: "16GB/8 CPUs · 512 GB SSD disk",
  },
  {
    title: "Enterprise",
    content: "32GB/12 CPUs · 1024 GB SSD disk",
  },
];
const selectedIndex = ref(null);

function selectItem(index) {
  if (selectedIndex.value === index) {
    selectedIndex.value = null;
  } else {
    selectedIndex.value = index;
  }
}
</script>
