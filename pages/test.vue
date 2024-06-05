<template>
  <div class="flex flex-row justify-center mt-5 space-x-1">
    <!-- nút chữ nghiêng -->
    <button
      @click="isItalic = !isItalic"
      :class="{
        'bg-green-600': isItalic,
      }"
      class="p-2 rounded border"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="1.2em"
        height="1.2em"
        viewBox="0 0 24 24"
      >
        <path
          fill="none"
          stroke="black"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M11 5h6M7 19h6m1-14l-4 14"
        />
      </svg>
    </button>

    <!-- nút chữ đậm -->
    <button
      @click="isBold = !isBold"
      :class="{
        'bg-green-600': isBold,
      }"
      class="p-2 rounded border"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="1.2em"
        height="1.2em"
        viewBox="0 0 15 15"
      >
        <path
          fill="black"
          d="M5.105 12c-.397 0-.681-.088-.853-.264c-.168-.18-.252-.465-.252-.853V4.117c0-.397.086-.681.258-.853c.176-.176.458-.264.847-.264H9.03c1.108 0 2.025.982 2.025 2.185c0 .9-.45 1.634-1.35 2.051c1.162.213 1.814 1.392 1.814 2.245c0 1.031-.528 2.519-2.24 2.519zm3.274-3.997H5.8v2.628h2.579c.521 0 1.25-.51 1.25-1.332c0-.823-.729-1.296-1.25-1.296M5.8 4.37v2.327h2.38c.36 0 1.097-.337 1.097-1.196c0-.86-.797-1.131-1.097-1.131z"
        />
      </svg>
    </button>

    <!-- nút chữ gạch dưới -->
    <button
      @click="isUnderline = !isUnderline"
      :class="{
        'bg-green-600': isUnderline,
      }"
      class="p-2 rounded border"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="1.2em"
        height="1.2em"
        viewBox="0 0 24 24"
      >
        <g fill="none">
          <path
            d="M24 0v24H0V0zM12.593 23.258l-.011.002l-.071.035l-.02.004l-.014-.004l-.071-.035c-.01-.004-.019-.001-.024.005l-.004.01l-.017.428l.005.02l.01.013l.104.074l.015.004l.012-.004l.104-.074l.012-.016l.004-.017l-.017-.427c-.002-.01-.009-.017-.017-.018m.265-.113l-.013.002l-.185.093l-.01.01l-.003.011l.018.43l.005.012l.008.007l.201.093c.012.004.023 0 .029-.008l.004-.014l-.034-.614c-.003-.012-.01-.02-.02-.022m-.715.002a.023.023 0 0 0-.027.006l-.006.014l-.034.614c0 .012.007.02.017.024l.015-.002l.201-.093l.01-.008l.004-.011l.017-.43l-.003-.012l-.01-.01z"
          />
          <path
            fill="black"
            d="M18 19a1 1 0 0 1 .117 1.993L18 21H6a1 1 0 0 1-.117-1.993L6 19zM17 3a1 1 0 0 1 .993.883L18 4v8a6 6 0 0 1-11.996.225L6 12V4a1 1 0 0 1 1.993-.117L8 4v8a4 4 0 0 0 7.995.2L16 12V4a1 1 0 0 1 1-1"
          />
        </g>
      </svg>
    </button>
  </div>
  <div class="flex justify-center">
    <div
      class="text-center w-full"
      :class="[
        ' mt-2 p-5 rounded ',
        { italic: isItalic },
        { 'font-bold': isBold },
        { underline: isUnderline },
        { 'text-right': isTextRight },

        isUnderline
          ? 'bg-blue-200'
          : isBold
          ? 'bg-blue-200'
          : isItalic
          ? 'bg-blue-200'
          : isTextRight
          ? 'bg-blue-200'
          : 'bg-slate-100',
      ]"
    >
      Trạng thái văn bản thay đổi ở đây
    </div>
  </div>
</template>

<script setup>
const isItalic = ref(false);
const isBold = ref(false);
const isUnderline = ref(false);
</script>
