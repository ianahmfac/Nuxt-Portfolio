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
    class="content-doc-full prose-pre:bg-gray-50 dark:prose-pre:bg-slate-900 prose-pre:text-slate-800 dark:prose-pre:text-gray-100"
  >
    <ContentDoc v-slot="{ doc }">
      <div class="grid md:grid-cols-8 grid-cols-1 md:gap-16 gap-2">
        <div class="md:col-span-6 col-auto">
          <!-- Menampilkan content isi dari doc -->
          <ContentRenderer :value="doc" />
        </div>

        <!-- Menampilkan Table of Content -->
        <div class="md:col-span-2 not-prose col-auto">
          <aside class="sticky top-8">
            <div class="font-bold mb-2">Table of Content</div>
            <nav>
              <TocLink :links="doc.body.toc.links" />
            </nav>
          </aside>
        </div>
      </div>
    </ContentDoc>
  </article>
</template>
