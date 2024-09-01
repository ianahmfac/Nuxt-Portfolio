<script setup>
const route = useRoute();
definePageMeta({
  layout: "blog",
});
</script>

<template>
  <h1>{{ route.params.slug }}</h1>
  <p>This is a blog page</p>
</template>
