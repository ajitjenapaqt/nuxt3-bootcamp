<template>
    <div class="mt-32 flex">
      <NuxtErrorBoundary>
        <CarSideBar />
        <NuxtPage />
        <template #error="{error}">
          <div class="text-center mx-auto flex flex-col">
            <h1 class="text-5xl text-red-600 mb-4">Sorry, something went wrong</h1>
            <code>{{ error }}</code>
            <button class="text-white bg-blue-400 px-10 py-3 rounded mt-4" @click="error.value = null">
              Go Back
            </button>
          </div>
        </template>
      </NuxtErrorBoundary>
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
