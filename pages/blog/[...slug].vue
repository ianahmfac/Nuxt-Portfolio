<!-- penambahan [...slug] untuk keperluan pembacaan url mendalam -->
<!-- Contohnya mengambil dari path: content/blog/markdown.md -->
<!-- Ketika kita mencari blog/markdown, maka akan ditrace sampai ke dalam" folder atau url -->

<script setup>
useHead({
  title: "Blog",
});
</script>

<template>
  <!-- prose:pre => Untuk styling pada code block -->
  <article
    class="prose dark:prose-invert prose-pre:bg-gray-50 dark:prose-pre:bg-slate-900 prose-pre:text-slate-800 dark:prose-pre:text-gray-100"
  >
    <ContentDoc />
  </article>
</template>
