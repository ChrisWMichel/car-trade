<template>
  <div>
    <div class="mt-5">
      <p class="mb-10">{{ description }}</p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  description: {
    type: String,
    required: true
  }
})
</script>

<style>

</style>