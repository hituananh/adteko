<script setup>
useHead({
  htmlAttrs: { lang: "en-AU" },
  title: "ADTEKO Pty Ltd — Advanced Thinking. Advanced Future.",
  meta: [
    {
      name: "description",
      content:
        "ADTEKO Pty Ltd provides technical consulting, engineering support, procurement, steel detailing, and civil project assistance across Australia. Based in Coffs Harbour, NSW.",
    },
    { property: "og:title", content: "ADTEKO Pty Ltd — Advanced Thinking. Advanced Future." },
    { property: "og:description", content: "Technical consulting, engineering support, procurement and civil project assistance across Australia." },
    { name: "robots", content: "index, follow" },
  ],
  link: [
    { rel: "preconnect", href: "https://fonts.googleapis.com" },
    { rel: "preconnect", href: "https://fonts.gstatic.com", crossorigin: "anonymous" },
    {
      rel: "stylesheet",
      href: "https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@500;600;700;800&family=Barlow:wght@300;400;500;600&display=swap",
    },
  ],
  bodyAttrs: {
    class: "font-body antialiased",
  },
});
</script>

<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>
