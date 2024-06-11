<template>
  <div class="flex items-center justify-center bg-white text-white">
    <div class="relative mx-6 h-96 w-[32rem] sm:mx-auto">
      <div ref="boxContainer" aria-haspopup="listbox">
        <button
          @click="showList = !showList"
          class="relative w-full rounded-lg border border-slate-300 bg-slate-90 px-3 py-2 focus:outline-none focus:ring-2 focus:ring-indigo-500 dark:border-slate-600"
          aria-expanded="showList"
          aria-controls="destination-dropdown"
          aria-labelledby="dropdown-label"
        >
          <span id="dropdown-label">{{
            selectedDestination.name || "Select A Destination"
          }}</span>
          <span
            class="absolute right-3 top-1/2 -translate-y-1/2"
            aria-hidden="true"
          >
            <ChevronDownIcon
              class="size-6 transition-transform duration-500"
              :class="showList ? 'rotate-180' : 'rotate-0 '"
            />
          </span>
        </button>
      </div>

      <div
        v-show="showList"
        class="absolute z-10 mt-1 w-full overflow-hidden rounded-lg border border-slate-300 bg-white shadow-md dark:border-slate-600 dark:bg-slate-900"
        id="destination-dropdown"
        role="listbox"
        aria-labelledby="dropdown-label"
        tabindex="-1"
      >
        <input
          type="text"
          v-model="searchTerm"
          ref="searchInput"
          placeholder="Search Destination"
          class="w-full rounded-t-lg border-b bg-white px-3 py-2 focus:border-indigo-400 focus:outline-none dark:border-slate-600 dark:bg-slate-900 dark:focus:border-indigo-700"
          role="searchbox"
        />
        <div class="h-96 overflow-y-auto combo-box-scrollbar">
          <div
            v-for="destination in filteredDestinations"
            :key="destination"
            @click="selectDestination(destination)"
            class="flex cursor-pointer items-center gap-3 px-3 py-2 hover:bg-indigo-500 hover:text-white focus:outline-none focus:ring-2 focus:ring-indigo-500 dark:hover:bg-indigo-700 dark:focus:ring-indigo-700"
            role="option"
            :aria-selected="selectedDestination === destination"
            tabindex="0"
            @keypress.enter="selectDestination(destination)"
          >
            <img
              :src="destination.imageUrl"
              alt=""
              class="size-10 rounded object-cover"
            />
            <div>
              <p class="font-medium">{{ destination.name }}</p>
              <p class="text-sm">{{ destination.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ChevronDownIcon } from "@heroicons/vue/24/outline";
import { ref, computed, onMounted, onUnmounted } from "vue";

const travelDestinations = ref([
  {
    name: "Paris, France",
    description: "City of romance and iconic landmarks.",
    imageUrl:
      "https://images.unsplash.com/photo-1499856871958-5b9627545d1a?q=80&w=600",
  },
  {
    name: "Santorini, Greece",
    description: "Whitewashed villages and breathtaking sunsets.",
    imageUrl:
      "https://images.unsplash.com/photo-1563789031959-4c02bcb41319?q=80&w=600",
  },
  {
    name: "Rome, Italy",
    description: "Ancient ruins, vibrant piazzas, and delicious cuisine.",
    imageUrl:
      "https://images.unsplash.com/photo-1515542622106-78bda8ba0e5b?q=80&w=600",
  },
  {
    name: "Iceland",
    description: "Volcanic landscapes, glaciers, and the Northern Lights.",
    imageUrl:
      "https://images.unsplash.com/photo-1476610182048-b716b8518aae?q=80&w=600",
  },
  {
    name: "Amsterdam, Netherlands",
    description: "Charming canals, world-class museums, and lively atmosphere.",
    imageUrl:
      "https://images.unsplash.com/photo-1584003564911-a7a321c84e1c?q=80&w=600",
  },
  {
    name: "Swiss Alps, Switzerland",
    description: "Majestic mountains, pristine lakes, and cozy villages.",
    imageUrl:
      "https://images.unsplash.com/photo-1586752488885-6ce47fdfd874?q=80&w=600",
  },
  {
    name: "Barcelona, Spain",
    description:
      "Architectural marvels, sandy beaches, and a buzzing nightlife.",
    imageUrl:
      "https://images.unsplash.com/photo-1578912996078-305d92249aa6?q=80&w=600",
  },
  {
    name: "Scottish Highlands, Scotland",
    description: "Rugged landscapes, historic castles, and a touch of mystery.",
    imageUrl:
      "https://images.unsplash.com/photo-1589490047559-a1c13ec25b87?q=80&w=600",
  },
  {
    name: "Prague, Czech Republic",
    description: "Fairytale city with gothic architecture and a rich history.",
    imageUrl:
      "https://images.unsplash.com/photo-1541849546-216549ae216d?q=80&w=600",
  },
  {
    name: "Lapland, Finland",
    description: "Winter wonderland, reindeer, and a chance to see Santa.",
    imageUrl:
      "https://images.unsplash.com/photo-1581853230165-b71de20b7f37?q=80&w=600",
  },
]);

const selectedDestination = ref("");
const searchTerm = ref("");
const showList = ref(false);
const boxContainer = ref(null);
const searchInput = ref(null);

function selectDestination(destination) {
  selectedDestination.value = destination;
  searchTerm.value = "";
  showList.value = false;
}

const filteredDestinations = computed(() => {
  return travelDestinations.value.filter((destination) =>
    destination.name.toLowerCase().startsWith(searchTerm.value.toLowerCase())
  );
});

function closeDropdown(event) {
  if (
    !boxContainer.value.contains(event.target) &&
    !searchInput.value.contains(event.target)
  ) {
    searchTerm.value = "";
    showList.value = false;
  }
}

onMounted(() => {
  window.addEventListener("click", closeDropdown);
});

onUnmounted(() => {
  window.removeEventListener("click", closeDropdown);
});
</script>
