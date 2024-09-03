<script setup>
useHead({
  title: "Blog",
});

const { data: posts } = await useAsyncData("blog-list", () => {
  return queryContent("blog").only(["_path", "title"]).find();
});
</script>

<template>
  <section class="prose dark:prose-invert">
    <h1 class="text-2xl font-bold mb-10">Blog</h1>
    <ul>
      <li v-for="post in posts" :key="post._path">
        <NuxtLink :to="post._path">{{ post.title }}</NuxtLink>
      </li>
    </ul>
  </section>
</template>
