<template>
  <div >
    
      <car-cards v-if="cars.length" :cars="cars" />
      <div v-else class="text-center text-2xl mt-10">Sorry, no cars found</div>
  </div>
</template>

<script setup>
import useFetchCars from '~/composibles/useFetchCars';
  const route = useRoute();
  const maxPrice = computed(() => route.query.maxPrice)
  const minPrice = computed(() => route.query.minPrice)

  const {data:cars, refresh} = await useFetchCars(route.params.city,{
    make: route.params.make,
    minPrice,
    maxPrice
  });
  watch(
    () => route.query,
    () => {
      refresh();
    }
  )
</script>