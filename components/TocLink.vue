<script setup>
const route = useRoute();
const { links, level } = defineProps({
  links: Array,
  level: {
    type: Number,
    default: 0,
  },
  activeId: {
    type: String,
    default: null,
  },
});
</script>

<template>
  <ul>
    <li v-for="link in links" :key="link.id">
      <NuxtLink
        :to="{ path: route.path, hash: `#${link.id}` }"
        class="hover:font-semibold hover:underline"
        :class="{
          'ml-4': level > 0,
          'text-green-600 dark:text-green-400': activeId === link.id,
        }"
      >
        - {{ link.text }}
      </NuxtLink>
      <TocLink v-if="link.children" :links="link.children" :level="level + 1" />
    </li>
  </ul>
</template>
