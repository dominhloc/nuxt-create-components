<template>
  <div class="flex flex-col justify-center items-center">
    <div
      class="container w-fit h-96 bg-slate-50 p-6 space-y-0 rounded-md overflow-y-auto"
    >
      <div class="flex justify-between items-center mb-4">
        <button
          class="border border-black h-7 w-7 shadow-lg p-1 rounded-md font-semibold flex justify-center items-center duration-300 hover:bg-slate-400"
          @click="updateMonth(-1)"
        >
          &lt;
        </button>
        <h2 class="text-xl font-bold p-1 border rounded-md shadow-lg">
          {{ currentMonth }}
        </h2>
        <button
          class="border border-black h-7 w-7 shadow-lg p-1 rounded-md font-semibold flex justify-center items-center duration-300 hover:bg-slate-400"
          @click="updateMonth(1)"
        >
          &gt;
        </button>
      </div>
      <div class="flex justify-center font-serif">
        {{ selectedDate }} {{ currentMonth }} {{}}
      </div>

      <div class="">
        <div class="grid grid-cols-7 gap-4 p-1 border rounded-md">
          <div
            v-for="(day, index) in weekDays"
            :key="index"
            class="text-center text-green-600 rounded-md w-14 border"
          >
            {{ day }}
          </div>
          <div
            v-for="(date, index) in calendarDates"
            :key="index"
            class="text-center rounded-md"
            @click="selectDate(date)"
            :class="{
              'bg-blue-500 font-bold hover:bg-blue-600 text-white':
                date.isToday || date.isSelected,
              'font-normal text-decoration: underline':
                date.isSelected && !date.disabled,
              'cursor-pointer border': !date.disabled,
            }"
          >
            {{ date.day }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
//
// Danh sách các tháng
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

// Danh sách các ngày trong tuần
const weekDays = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"];

// Biến lưu trữ tháng và năm hiện tại
const currentMonthIndex = ref(new Date().getMonth());
const currentYear = ref(new Date().getFullYear());

// Biến lưu trữ ngày được chọn
const selectedDate = ref(null);

// Tính toán tháng hiện tại dưới dạng chuỗi
const currentMonth = computed(
  () => `${months[currentMonthIndex.value]} ${currentYear.value}`
);

// Hàm tính số ngày trong tháng
const daysInMonth = (month, year) => new Date(year, month, 0).getDate();

// Hàm kiểm tra xem ngày đầu tiên của tháng có phải là chủ nhật không
const isFirstDayOfMonth = (date) =>
  new Date(currentYear.value, currentMonthIndex.value, date).getDay() === 0;

// Hàm kiểm tra xem ngày hiện tại có phải là hôm nay không
const isToday = (date) =>
  date === new Date().getDate() &&
  currentMonthIndex.value === new Date().getMonth() &&
  currentYear.value === new Date().getFullYear();

// Hàm tính ngày bắt đầu của tháng
const getStartingDay = (month, year) => {
  const day = new Date(year, month, 1).getDay();
  return day === 0 ? 6 : day - 1; // Điều chỉnh để Thứ Hai là ngày đầu tiên trong tuần
};

// Tính toán các ngày trong lịch
const calendarDates = computed(() => {
  const daysInCurrentMonth = daysInMonth(
    currentMonthIndex.value + 1,
    currentYear.value
  );
  const startingDay = getStartingDay(
    currentMonthIndex.value,
    currentYear.value
  );

  const dates = [];

  // Thêm các ngày trống trước ngày đầu tiên của tháng
  for (let i = 0; i < startingDay; i++) {
    dates.push({
      day: "",
      disabled: true,
    });
  }

  // Thêm các ngày thực tế trong tháng
  for (let i = 1; i <= daysInCurrentMonth; i++) {
    dates.push({
      day: i,
      isSelected: selectedDate.value === i,
      isToday: isToday(i),
      disabled: false,
    });
  }
  return dates;
});

// Hàm cập nhật tháng
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

// Hàm chọn ngày
const selectDate = (date) => {
  if (!date.disabled) {
    selectedDate.value = date.day;
  }
};
</script>
