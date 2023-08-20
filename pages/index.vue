<template>
  <div>
    <h1>Welcome to the homepage</h1>
  </div>
</template>

<script setup lang="ts">
const { data: image } = await useFetch(
  `https://api.slingacademy.com/v1/sample-data/photos/${Math.floor(
    Math.random() * 100 + 1,
  )}`,
);

useSeoMeta({
  title: () => image?.photo?.title,
  ogTitle: () => image?.photo?.title,
  description: () => image?.photo?.description,
  ogDescription: () => image?.photo?.description,
  ogImage: () => image?.photo?.url,
  twitterCard: () => image?.photo?.description,
});
</script>
