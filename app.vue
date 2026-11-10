<script setup>
useHead({
  htmlAttrs: { lang: "en-AU" },
  title: "ADTEKO Pty Ltd — Advanced Thinking. Advanced Future.",
  meta: [
    {
      name: "description",
      content:
        "ADTEKO Pty Ltd: BIM & 3D visualisation from 2D drawings, building & farming supplies, and project & contract management across Australia. Based in Coffs Harbour, NSW.",
    },
    { property: "og:title", content: "ADTEKO Pty Ltd — Advanced Thinking. Advanced Future." },
    { property: "og:description", content: "BIM & 3D visualisation, building & farming supplies, and project & contract management across Australia." },
    { name: "robots", content: "index, follow" },
    { name: "theme-color", content: "#5C1A4E" },
  ],
  link: [
    { rel: "icon", type: "image/x-icon", href: "/favicon.ico" },
    { rel: "icon", type: "image/png", sizes: "32x32", href: "/favicon-32x32.png" },
    { rel: "apple-touch-icon", sizes: "180x180", href: "/apple-touch-icon.png" },
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
