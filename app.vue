<script setup>
const route = useRoute();

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
</script>

<template>
  <NuxtLayout>
    <NuxtPage />
    <h1>Current Route: {{ route.path }}</h1>
  </NuxtLayout>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: "Open Sans";
}
</style>
