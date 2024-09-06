<template>
  <header class="flex justify-between items-start md:items-center mt-5">
    <div class="flex items-center md:space-x-12">
      <div class="hidden md:block">
        <NuxtLink
          to="/"
          class="link logo"
          style="font-family: 'Protest Guerrilla'"
          >Portfolio</NuxtLink
        >
      </div>
      <nav class="font-mono">
        <ul class="flex flex-col md:flex-row md:gap-4">
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
  @apply p-2 hover:bg-gray-200 hover:dark:bg-slate-900 text-xl md:text-base;
}

.logo {
  @apply text-3xl font-semibold p-2 hover:bg-gray-200 hover:dark:bg-slate-900;
}
</style>
