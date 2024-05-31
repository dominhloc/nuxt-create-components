<template>
  <div><Tabs :tabs="tabs" /></div>
</template>

<script setup>
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
</script>
