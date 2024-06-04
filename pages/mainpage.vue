<template>
  <div
    class="flex flex-col justify-center space-y-5 p-6 min-h-screen bg-gradient-to-l from-gray-900 to-gray-900"
  >
    <div class="text-white font-serif text-2xl text-center">Toggle Switch</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 h-32 flex justify-center items-center"
    >
      <ToggleSwitch />
    </div>
    <div class="text-white text-center font-serif text-2xl">Slider</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Slider />
    </div>
    <div class="text-white text-center font-serif text-2xl">Calendar</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Calendar />
    </div>
    <div class="text-white text-center font-serif text-2xl">Scroll</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Scroll :list="list" />
    </div>
    <div class="text-white text-center font-serif text-2xl">Dropdown</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Dropdown />
    </div>
    <div class="text-white text-center font-serif text-2xl">Pagination</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Pagination />
    </div>
    <div class="text-white text-center font-serif text-2xl">Accordion</div>

    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Accordion :accordion="accordion" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Combobox</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Combobox :data="data" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Dialog</div>

    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Dialog :dialog="dialog" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Alert</div>

    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Alert :alert="alert" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Editable</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Editable :list="list1" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Radio Group</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Radio :radiogroup="radiogroup" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Hovercard</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Hovercard :data="data1" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Tabs</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Tabs :tabs="tabs" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Tags Input</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <TagsInput :fruit="fruit" />
    </div>

    <div class="text-white text-center font-serif text-2xl">
      Navigation Menu
    </div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <NavigationMenu :tabs1="tabs1" />
    </div>

    <div class="text-white text-center font-serif text-2xl">Number Field</div>
    <div
      class="bg-gradient-to-l from-green-700 to-green-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <NumberField />
    </div>
  </div>
</template>

<script setup>
const dropdownData = [
  { label: "Option 1" },
  { label: "Option 2" },
  { label: "Option 3" },
  { label: "Option 4" },
  { label: "Option 5" },
  { label: "Option 6" },
  { label: "Option 7" },
  { label: "Option 8" },
  { label: "Option 9" },

  // Add more options as needed
];

const list = ref([
  { name: "v1.2.0-beta.1" },
  { name: "v1.2.0-beta.2" },
  { name: "v1.2.0-beta.3" },
  { name: "v1.2.0-beta.4" },
  { name: "v1.2.0-beta.5" },
  { name: "v1.2.0-beta.6" },
  { name: "v1.2.0-beta.7" },
  { name: "v1.2.0-beta.8" },
  { name: "v1.2.0-beta.9" },
  { name: "v1.2.0-beta.10" },
  { name: "v1.2.0-beta.11" },
  { name: "v1.2.0-beta.12" },
  { name: "v1.2.0-beta.13" },
  { name: "v1.2.0-beta.14" },
  { name: "v1.2.0-beta.15" },
  { name: "v1.2.0-beta.16" },
  { name: "v1.2.0-beta.17" },
  { name: "v1.2.0-beta.18" },
  { name: "v1.2.0-beta.19" },
  { name: "v1.2.0-beta.20" },
  { name: "v1.2.0-beta.21" },
  { name: "v1.2.0-beta.22" },
  { name: "v1.2.0-beta.23" },
  { name: "v1.2.0-beta.24" },
  { name: "v1.2.0-beta.25" },
]);

const accordion = [
  {
    id: "item-1",
    title: "Is it accessible?",
    content: "Yes. It adheres to the WAI-ARIA design pattern.",
  },
  {
    id: "item-2",
    title: "Is it unstyled?",
    content:
      "Yes. It's unstyled by default, giving you freedom over the look and feel.",
  },
  {
    id: "item-3",
    title: "Can it be animated?",
    content: "Yes! You can use the transition prop to configure the animation.",
  },
];

const data = ref([
  {
    label: "Text A",
    value: 1,
  },
  {
    label: "Text B",
    value: 2,
  },
  {
    label: "Text C",
    value: 3,
  },
  {
    label: "Text D",
    value: 4,
  },
  {
    label: "Text E",
    value: 5,
  },
  {
    label: "Text F",
    value: 6,
  },
]);

const list1 = ref([
  { id: 1, name: "Nội Dung 1", done: false, editname: "Nội Dung 1" },
  { id: 2, name: "Nội Dung 2", done: false, editname: "Nội Dung 2" },
  { id: 3, name: "Nội Dung 3", done: false, editname: "Nội Dung 3" },
]);

const data1 = [
  {
    title: "Radix",
    user: "@radix_ui",
    content:
      "Components, icons, colors, and templates for building high-quality, accessible UI. Free and open-source.",
    comments: "0 Following - 2,900 Followers",
  },
];

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

const tabs = [
  {
    title: "Recent",
    contents: [
      {
        content: "Does drinking coffee make you smarter?",
        comments: "5h ago - 5 likes - 5 shares",
      },
      {
        content: "So you've bought coffee... now what?",
        comments: "1h ago - 2 likes - 3 shares",
      },
    ],
  },
  {
    title: "Popular",
    contents: [
      {
        content: "Is tech making coffee better or worse?",
        comments: "Jan 7 - 8 likes - 9 shares",
      },
      {
        content: "The most innovative things happening in coffee",
        comments: "Mar 19 - 20 likes - 21 shares",
      },
    ],
  },
  {
    title: "Trending",
    contents: [
      {
        content: "Ask Me Anything: 10 answers to your questions about coffee",
        comments: "2d ago - 3 likes - 4 shares",
      },
      {
        content: "The worst advice we've ever heard about coffee",
        comments: "4d ago - 4 likes - 4 shares",
      },
    ],
  },
];

const fruit = ref([
  { id: 1, name: "Apple" },
  { id: 2, name: "Banana" },
  { id: 3, name: "Orange" },
  { id: 4, name: "Lemon" },
]);

const alert = [
  {
    title: " Are you absolutely sure?",
    content:
      "This action cannot be undone. This will permanently delete your account and remove your data from our servers.",
  },
];

const dialog = [
  {
    title: " Edit profile",
    content: "Make changes to your profile here. Click save when you're done.",
  },
];

const tabs1 = [
  {
    title: "Learn",
    contents: [
      {
        content: "Stitches",
        comments: "CSS-in-JS with best-in-class developer experience.",
      },
      {
        content: "Colors",
        comments: "Beautiful, thought-out palettes with auto dark mode",
      },
      {
        content: "Icons",
        comments: "A crisp set of 15x15 icons, balanced and consistent",
      },
    ],
  },
  {
    title: "Overview",
    contents: [
      {
        content: "Introduction",
        comments: "Build high-quality, accessible design systems and web apps.",
      },
      {
        content: "Getting started",
        comments:
          "A quick tutorial to get you up and running with Radix Primitives.",
      },
      {
        content: "Styling",
        comments: "Unstyled and compatible with any styling solution.",
      },
    ],
  },
  {
    title: "Overview 2",
    contents: [
      {
        content: "Animation",
        comments: "Use CSS keyframes or any animation library of your choice.",
      },
      {
        content: "Accessibility",
        comments: "Tested in a range of browsers and assistive technologies.",
      },
      {
        content: "Releases",
        comments: "Radix Primitives releases and their changelogs.",
      },
    ],
  },
];
</script>
