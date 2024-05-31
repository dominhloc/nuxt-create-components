<template>
  <div class="container mx-auto">
    <div class="flex justify-between items-center mb-4">
      <button @click="updateMonth(-1)">&lt;</button>
      <h2 class="text-xl font-bold">{{ currentMonth }}</h2>
      <button @click="updateMonth(1)">&gt;</button>
    </div>
    <div class="grid grid-cols-7 gap-2">
      <div
        v-for="(day, index) in weekDays"
        :key="index"
        class="text-center font-bold"
      >
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
  </div>
</template>

<script setup>
import { ref, computed } from "vue";

const months = [
  "January",
  "February",
  "March",
  "April",
  "May",
  "June",
  "July",
  "August",
  "September",
  "October",
  "November",
  "December",
];
const weekDays = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];

const currentMonthIndex = ref(new Date().getMonth());
const currentYear = ref(new Date().getFullYear());
const selectedDate = ref(null);

const currentMonth = computed(
  () => `${months[currentMonthIndex.value]} ${currentYear.value}`
);

const daysInMonth = (month, year) => new Date(year, month, 0).getDate();
const isFirstDayOfMonth = (date) =>
  new Date(currentYear.value, currentMonthIndex.value, date).getDay() === 0;
const isToday = (date) =>
  date === new Date().getDate() &&
  currentMonthIndex.value === new Date().getMonth() &&
  currentYear.value === new Date().getFullYear();

const calendarDates = computed(() => {
  const daysInCurrentMonth = daysInMonth(
    currentMonthIndex.value + 1,
    currentYear.value
  );
  const dates = [];
  for (let i = 1; i <= daysInCurrentMonth; i++) {
    dates.push({
      day: i,
      isSelected: selectedDate.value === i,
      isToday: isToday(i),
      disabled: false,
    });
  }
  return Array.from(
    {
      length: isFirstDayOfMonth(1)
        ? 0
        : 7 - new Date(currentYear.value, currentMonthIndex.value, 1).getDay(),
    },
    () => ({ day: "", disabled: true })
  ).concat(dates);
});

const updateMonth = (offset) => {
  const newMonth = currentMonthIndex.value + offset;
  currentMonthIndex.value = newMonth < 0 ? 11 : newMonth > 11 ? 0 : newMonth;
  currentYear.value =
    newMonth < 0
      ? currentYear.value - 1
      : newMonth > 11
      ? currentYear.value + 1
      : currentYear.value;
};

const selectDate = (date) => {
  if (!date.disabled) {
    selectedDate.value = date.day;
  }
};
</script>
