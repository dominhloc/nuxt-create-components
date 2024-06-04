<template>
  <div><NavigationMenu :tabs1="tabs1" /></div>
</template>

<script setup>
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
