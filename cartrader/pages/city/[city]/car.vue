<template>
    <div class="mt-32 flex">
      <CarSideBar />
      <NuxtPage />
    </div>
</template>

<script setup>
import {useUtilities} from "~/composables/useUtilities";

const route = useRoute()
const {capitalizeFirstLetter} = useUtilities()
const city = capitalizeFirstLetter(route.params.city)
const make = capitalizeFirstLetter(route.params.make)

useHead({
  title: `${make ?? 'Cars'} in ${city}`
})

definePageMeta({
  layout: "custom"
})
</script>
