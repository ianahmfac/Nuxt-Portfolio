<template>
  <header class="flex justify-between items-center mt-5">
    <div class="flex items-center space-x-12">
      <div>
        <NuxtLink to="/" class="text-xl font-semibold link">
          Portfolio
        </NuxtLink>
      </div>
      <nav class="font-mono">
        <ul class="flex gap-4">
          <li>
            <NuxtLink to="/" class="link">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about" class="link">About</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/project" class="link">Project</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/blog" class="link">Blog</NuxtLink>
          </li>
        </ul>
      </nav>
    </div>

    <!-- Memastikan component hanya dirender pada sisi client, bukan pada server -->
    <ClientOnly>
      <ColorModeSelector />
    </ClientOnly>
  </header>
</template>

<style scoped>
.link {
  @apply p-2 hover:bg-gray-200 hover:dark:bg-slate-900;
}
</style>
