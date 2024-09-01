<template>
  <div class="container mx-auto">
    <header class="flex justify-between items-center">
      <div>
        <NuxtLink to="/" class="text-xl font-semibold p-2 hover:bg-gray-200">
          Portfolio
        </NuxtLink>
      </div>
      <nav class="font-mono">
        <ul class="flex gap-4">
          <li>
            <NuxtLink to="/">Home</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/about">About</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/blog">Blog</NuxtLink>
          </li>
        </ul>
      </nav>
    </header>
    <main class="p-2">
      <slot />
    </main>
  </div>
</template>
