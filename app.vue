<script setup lang="ts">
useHead({
  title: "Heitor Schleder",
  meta: [
    { name: "description", content: "Heitor Schleder é um desenvolvedor full-stack." },
    { name: "keywords", content: "Heitor Schleder, Full Cycle, DevOps, Desenvolvedor Full Stack, Programação, Front-End, Back-End" },
    { name: "author", content: "Heitor Schleder" },
    { property: "og:title", content: "Heitor Schleder" },
    { property: "og:description", content: "Desenvolvedor full-stack." },
    { property: "og:type", content: "website" }
  ],
  link: [
    { rel: 'icon', href: '/favicon.ico'},
    { rel: "stylesheet", href: "https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/dist/tabler-icons.min.css" },]
});
</script>
<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>
