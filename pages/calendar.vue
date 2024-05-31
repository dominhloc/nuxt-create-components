<template>
  <div>
    <div>
      <button @click="updateMonth(-1)">&lt;</button>
      <h2 class="text-xl font-bold">{{ currentMonth }}</h2>
      <button @click="updateMonth(1)">&gt;</button>
    </div>
    <div v-for="(day, index) in weekDays" :key="index" class="text-center">
      {{ day }}
    </div>
    <div
      v-for="(date, index) in calendarDates"
      :key="index"
      @click="selectDate(date)"
      :class="{
        'bg-gray-200': date.isToday || date.isSelected,
        'font-bold': date.isSelected && !date.disabled,
        'cursor-pointer': !date.disabled,
      }"
    >
      {{ date.day }}
    </div>
  </div>
</template>

<script setup>
const months = [
  "January - Tháng 1",
  "February - Tháng 2",
  "March - Tháng 3",
  "April - Tháng 4",
  "May - Tháng 5",
  "June - Tháng 6",
  "July - Tháng 7",
  "August - Tháng 8",
  "September - Tháng 9",
  "October - Tháng 10",
  "November - Tháng 11",
  "December - Tháng 12",
];

const weekDays = [
  "Sun -  Chủ Nhật",
  "Mon - Thứ 2",
  "Tue - Thứ 3",
  "Wed - Thứ 4",
  "Thu - Thứ 5",
  "Fri - Thứ 6",
  "Sat - Thứ 7",
];

const currentMonthIndex = ref(new Date().getMonth());
const currentYear = ref(new Date().getFullYear());
const selectedDate = ref(null);

const currentMonth = computed(
  () => `${months[currentMonthIndex.value]} ${currentYear.value}`
);

</script>
