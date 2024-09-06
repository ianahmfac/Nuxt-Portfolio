<script setup>
const { limit } = defineProps({
  limit: {
    type: Number,
    default: null,
  },
});
</script>

<template>
  <BlogList v-slot="{ posts }" :limit="limit">
    <div v-for="post in posts" :key="post.id">
      <NuxtLink :to="post._path">{{ post.title }}</NuxtLink>
    </div>
  </BlogList>
</template>
