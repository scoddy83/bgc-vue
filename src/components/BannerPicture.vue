<script setup lang="ts">
  import sanity from '../services/client'
  import imageUrlBuilder from "@sanity/image-url";
  const imageBuilder = imageUrlBuilder(sanity);

  defineProps([
    '_Page'
  ])

  const query = `*[_type == "banner" && page == _Page] {
    page,
    bild,
    pageTitle,
    shortText
  }[0...10]`;

  const banner = await sanity.fetch(query);

  function imageUrlFor(source:string) : any {
    return imageBuilder.image(source);
  }
</script>

<template>
  <div class="hero min-h-screen banner">
    <div class="hero-overlay bg-opacity-60"></div>
    <div class="hero-content text-center text-neutral-content">
      <div class="max-w-md">
        <h1 class="mb-5 text-5xl font-bold">{{ banner[0].pageTitle }}</h1>
        <p class="mb-5">{{ banner[0].shortText }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.banner {
  background-image: url("imageUrlFor(bild)");
}
</style>