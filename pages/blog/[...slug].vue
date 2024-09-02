<!-- penambahan [...slug] untuk keperluan pembacaan url mendalam -->
<!-- Contohnya mengambil dari path: content/blog/markdown.md -->
<!-- Ketika kita mencari blog/markdown, maka akan ditrace sampai ke dalam" folder atau url -->

<script setup>
useHead({
  title: "Blog",
});
</script>

<template>
  <article class="prose dark:prose-invert">
    <ContentDoc />
  </article>
</template>
