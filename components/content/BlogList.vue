<script setup>
const { data: posts } = await useAsyncData("blog-list", () => {
  return (
    queryContent("blog")
      //   Exclude blog.md post
      .where({ _path: { $ne: "/blog" } })
      .only(["_path", "title"])
      .find()
  );
});
</script>

<template>
  <section class="not-prose">
    <ul>
      <li v-for="post in posts" :key="post._path">
        <NuxtLink :to="post._path">{{ post.title }}</NuxtLink>
      </li>
    </ul>
  </section>
</template>
