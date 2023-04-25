<template>
  <div>
    <CarDetailHero />
    <CarDetailAttributes />
    <CarDetailDescription />
    <CarDetailContact />
  </div>
</template>

<script setup>
const {cars} = useCars()
const route = useRoute()
const {capitalizeFirstLetter} = useUtilities();

const car = computed(() => {
  return cars.find((car) => {
    return car.id === parseInt(route.params.id);
  })
})

useHead({
  title: capitalizeFirstLetter(route.params.name)
})

definePageMeta({
  layout: "custom"
})
</script>
