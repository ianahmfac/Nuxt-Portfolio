<script setup>
const route = useRoute();
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
}
</style>
