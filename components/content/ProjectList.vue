<script setup>
// $fetch: dilakukan dari sisi server
// useFetch: Dilakukan pada component setup
const { error, status, data } = await useFetch(
  "https://api.github.com/users/ianahmfac/repos",
  {
    lazy: true,
  }
);

const repos = computed(() => {
  return data.value.sort((a, b) => b.stargazers_count - a.stargazers_count);
});
</script>

<template>
  <section class="not-prose">
    <section v-if="status == 'pending'">Loading...</section>
    <section v-else-if="error">Something went wrong</section>
    <section v-else>
      <ul class="grid grid-cols-1 gap-4 mb-10">
        <div v-for="repo in repos" :key="repo.id">
          <a :href="repo.html_url" target="_blank">
            <li
              class="border border-gray-100 dark:border-slate-900 rounded-md p-4 font-mono hover:bg-gray-100 dark:hover:bg-slate-900 cursor-pointer"
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
          </a>
        </div>
      </ul>
    </section>
  </section>
</template>
