<script setup>
useHead({
  titleTemplate: "%s - Portfolio",
  link: [
    {
      rel: "preconnect",
      href: "https://fonts.googleapis.com",
    },
    {
      rel: "preconnect",
      href: "https://fonts.gstatic.com",
      crossorigin: "anonymous",
    },
    {
      href: "https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap",
      rel: "stylesheet",
    },
  ],
});

useSeoMeta({
  title: "Portfolio - ianahmfac",
  description: "This is my amazing portfolio site, let me tell you about it.",
  ogTitle: "Portfolio - ianahmfac",
  ogDescription: "This is my amazing portfolio site, let me tell you about it.",
  ogImage:
    "https://images.unsplash.com/photo-1472289065668-ce650ac443d2?q=80&w=2069&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  twitterCard: "summary_large_image",
  twitterTitle: "Portfolio - ianahmfac",
  twitterDescription:
    "This is my amazing portfolio site, let me tell you about it.",
});
</script>

<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: "Open Sans";
  @apply bg-white dark:bg-slate-800 text-slate-800 dark:text-gray-100;
}
</style>
