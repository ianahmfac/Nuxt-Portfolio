<script setup>
// $fetch: dilakukan dari sisi server
// useFetch: Dilakukan pada component setup
const {
  error,
  status,
  data: repos,
} = await useFetch("https://api.github.com/users/ianahmfac/repos");
console.log(repos);
</script>

<template>
  <div>
    <p class="mb-10">This is a list of my projects</p>
    <section v-if="status == 'pending'">Loading...</section>
    <section v-else-if="error">Something went wrong</section>
    <section v-else>
      <ul class="grid grid-cols-1 gap-4 mb-10">
        <li
          v-for="repo in repos"
          :key="repo.id"
          class="border border-gray-100 rounded-md p-4 font-mono hover:bg-gray-100 cursor-pointer"
        >
          <div class="grid grid-cols-12 items-center text-sm">
            <div class="col-span-11">
              <div class="font-semibold">{{ repo.name }}</div>
              <p v-if="repo.description" class="text-xs text-gray-400 mt-1">
                {{ repo.description }}
              </p>
            </div>
            <div class="text-end">{{ repo.stargazers_count }} ⭐️</div>
          </div>
        </li>
      </ul>
    </section>
  </div>
</template>
