<script setup>
const { error } = defineProps({ error: Object });
</script>

<template>
  <NuxtLayout>
    <section class="text-center">
      <h1 class="text-6xl mb-4">Oops {{ error.statusCode }}</h1>
      <h2 class="text-2xl text-gray-600 dark:text-gray-300">
        {{ error.statusMessage }}
      </h2>
    </section>
  </NuxtLayout>
</template>
