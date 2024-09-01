<script setup>
useHead({
  title: "Project",
});

// $fetch: dilakukan dari sisi server
// useFetch: Dilakukan pada component setup
const { error, status, data } = await useFetch(
  "https://api.github.com/users/ianahmfac/repos"
);
</script>
<template>
  <h1>Project Page</h1>
  <section v-if="status == 'pending'">Loading...</section>
  <section v-else-if="error">Something went wrong</section>
  <section v-else>{{ data }}</section>
</template>
