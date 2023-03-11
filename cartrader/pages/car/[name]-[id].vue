<template>
  <div>
      <CarDetailHero />
      <CarDetailAttributes />
      <CarDetailDescription />
      <CarDetailContact />
    </div>
</template>

<script setup>
import {useUtilities} from "~/composables/useUtilities";

const route = useRoute()
const {capitalizeFirstLetter} = useUtilities()

useHead({
  title: `${capitalizeFirstLetter(route.params.name)}`
})

definePageMeta({
  layout: "custom"
})
</script>
