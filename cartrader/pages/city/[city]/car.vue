<script setup>
const route = useRoute()
const city = route.params.city.toUpperCase()
const make = route.params.make

useHead({
  title: `${make ?? 'Cars'} in ${city}`
})

definePageMeta({
  layout: "custom"
})
</script>

<template>
    <div class="mt-32 flex">
      <CarSideBar />
      <NuxtPage />
    </div>
</template>
