<template>
  <div class="flex flex-col justify-center space-y-5 p-6 min-h-screen bg-white">
    <div class="text-slate-900 font-serif text-2xl text-center">
      Toggle Switch
    </div>
    <div
      class="bg-gradient-to-l from-red-700 to-red-300 shadow-md rounded-lg p-6 h-32 flex justify-center items-center"
    >
      <ToggleSwitch />
    </div>
    <div class="text-slate-900 text-center font-serif text-2xl">Slider</div>
    <div
      class="bg-gradient-to-l from-slate-600 to-slate-300 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Slider />
    </div>
    <div class="text-slate-900 text-center font-serif text-2xl">Calendar</div>
    <div
      class="bg-gradient-to-l from-orange-600 to-orange-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Calendar />
    </div>
    <div class="text-slate-900 text-center font-serif text-2xl">Scroll</div>
    <div
      class="bg-gradient-to-l from-blue-700 to-blue-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Scroll :list="list" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Label</div>
    <div
      class="bg-gradient-to-l from-emerald-700 to-emerald-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Label />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Dropdown</div>
    <div
      class="bg-gradient-to-l from-slate-700 to-slate-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Dropdown />
    </div>
    <div class="text-slate-900 text-center font-serif text-2xl">Pagination</div>
    <div
      class="bg-gradient-to-l from-emerald-700 to-emerald-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Pagination />
    </div>
    <div class="text-slate-900 text-center font-serif text-2xl">Accordion</div>

    <div
      class="bg-gradient-to-l from-red-700 to-red-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Accordion :accordion="accordion" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Combobox</div>
    <div
      class="bg-gradient-to-l from-stone-700 to-stone-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Combobox :data="data" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Dialog</div>

    <div
      class="bg-gradient-to-l from-sky-700 to-sky-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Dialog v-model:dialog="dialog" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Alert</div>

    <div
      class="bg-gradient-to-l from-lime-700 to-lime-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Alert :alert="alert" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Editable</div>
    <div
      class="bg-gradient-to-l from-teal-700 to-teal-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Editable :list="list1" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">
      Radio Group
    </div>
    <div
      class="bg-gradient-to-l from-yellow-700 to-yellow-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Radio :radiogroup="radiogroup" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Hovercard</div>
    <div
      class="bg-gradient-to-l from-cyan-700 to-cyan-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Hovercard :data="data1" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Tabs</div>
    <div
      class="bg-gradient-to-l from-emerald-700 to-emerald-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Tabs :tabs="tabs" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Tags Input</div>
    <div
      class="bg-gradient-to-l from-pink-700 to-pink-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <TagsInput :fruit="fruit" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">
      Navigation Menu
    </div>
    <div
      class="bg-gradient-to-l from-blue-700 to-blue-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <NavigationMenu :tabs1="tabs1" />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">
      Number Field
    </div>
    <div
      class="bg-gradient-to-l from-red-700 to-red-300 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <NumberField />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Separator</div>
    <div
      class="bg-gradient-to-l from-slate-700 to-slate-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Separator />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">
      Toggle Group
    </div>
    <div
      class="bg-gradient-to-l from-orange-700 to-orange-400 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <ToggleGroup />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Toast</div>
    <div
      class="bg-gradient-to-l from-neutral-700 to-lime-600 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <Toast />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">Avatar</div>
    <div
      class="bg-gradient-to-l from-pink-700 to-pink-400 shadow-md rounded-lg p-6 flex justify-center items-center space-x-10 mt-4"
    >
      <Avatar
        src="https://vntime.org/wp-content/uploads/2020/04/100-%E1%BA%A2nh-n%E1%BB%81n-m%C3%A1y-t%C3%ADnh-%C4%91%E1%BA%B9p-nh%E1%BA%A5t-c%C3%B3-link-t%E1%BA%A3i-v%E1%BB%81-tr%E1%BB%B1c-ti%E1%BA%BFp.jpeg"
        alt="User Avatar"
      />

      <Avatar
        src="https://cdn.vox-cdn.com/thumbor/pTa_yD0mbfDWi7AeAOA7Ym7R4qE=/1400x1400/filters:format(jpeg)/cdn.vox-cdn.com/uploads/chorus_asset/file/23102001/DF_12080_rv2_1000x563_thumbnail.jpg"
        alt="User Avatar"
      />

      <Avatar
        src="https://www.galaxycine.vn/media/2019/3/20/mv5bmti5ody5ntuzmf5bml5banbnxkftztcwotazntizmw--v1-sy1000-cr0-0-1420-1000-al-_1553074176319.jpg"
        alt="User Avatar"
      />
    </div>

    <div class="text-slate-900 text-center font-serif text-2xl">PinInput</div>
    <div
      class="bg-gradient-to-l from-neutral-700 to-orange-300 shadow-md rounded-lg p-6 flex justify-center items-center"
    >
      <PinInput />
    </div>
  </div>
</template>

<script setup>
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
  { name: "v1.2.0-beta.26" },
  { name: "v1.2.0-beta.27" },
  { name: "v1.2.0-beta.28" },
  { name: "v1.2.0-beta.29" },
  { name: "v1.2.0-beta.30" },
  { name: "v1.2.0-beta.31" },
  { name: "v1.2.0-beta.32" },
  { name: "v1.2.0-beta.33" },
  { name: "v1.2.0-beta.34" },
  { name: "v1.2.0-beta.35" },
  { name: "v1.2.0-beta.36" },
  { name: "v1.2.0-beta.37" },
  { name: "v1.2.0-beta.38" },
  { name: "v1.2.0-beta.39" },
  { name: "v1.2.0-beta.40" },
  { name: "v1.2.0-beta.41" },
  { name: "v1.2.0-beta.42" },
  { name: "v1.2.0-beta.43" },
  { name: "v1.2.0-beta.44" },
  { name: "v1.2.0-beta.45" },
  { name: "v1.2.0-beta.46" },
  { name: "v1.2.0-beta.47" },
  { name: "v1.2.0-beta.48" },
  { name: "v1.2.0-beta.49" },
  { name: "v1.2.0-beta.50" },
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
    title: "Overview 1",
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
