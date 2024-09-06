<!-- penambahan [...slug] untuk keperluan pembacaan url mendalam -->
<!-- Contohnya mengambil dari path: content/blog/markdown.md -->
<!-- Ketika kita mencari blog/markdown, maka akan ditrace sampai ke dalam" folder atau url -->

<script setup>
useHead({
  title: "Blog",
});

const activeId = ref(null);

onMounted(() => {
  const callback = (entries) => {
    for (const entry of entries) {
      if (entry.isIntersecting) {
        activeId.value = entry.target.id;
        break;
      }
    }
  };
  const observer = new IntersectionObserver(callback, {
    root: null,
    threshold: 0.5,
    rootMargin: "0px",
  });
  const element = document.querySelectorAll("h2", "h3");
  for (const el of element) {
    // Meng-observer hanya element h2 dan h3 saja
    observer.observe(el);
  }

  onBeforeUnmount(() => {
    for (const el of element) {
      observer.unobserve(el);
    }
  });
});
</script>

<template>
  <div>
    <!-- prose:pre => Untuk styling pada code block -->
    <article
      class="content-doc-full prose-pre:bg-gray-50 dark:prose-pre:bg-slate-900 prose-pre:text-slate-800 dark:prose-pre:text-gray-100"
    >
      <ContentDoc>
        <template v-slot="{ doc }">
          <div class="grid md:grid-cols-8 grid-cols-1 md:gap-16 gap-2">
            <div
              :class="{
                'md:col-span-6 col-auto': doc.tableOfContent,
                'col-span-8': !doc.tableOfContent,
              }"
            >
              <!-- Menampilkan content isi dari doc -->
              <ContentRenderer :value="doc" />
            </div>

            <!-- Menampilkan Table of Content -->
            <div
              class="hidden md:block md:col-span-2 not-prose"
              v-if="doc.tableOfContent"
            >
              <aside class="sticky top-8">
                <div class="font-bold mb-2">Table of Content</div>
                <nav>
                  <TocLink :links="doc.body.toc.links" :activeId="activeId" />
                </nav>
              </aside>
            </div>
          </div>
        </template>

        <template #not-found>
          <h1 class="text-4xl text-center">Page Not Found</h1>
        </template>
      </ContentDoc>
    </article>
  </div>
</template>
