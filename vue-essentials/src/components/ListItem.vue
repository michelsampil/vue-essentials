<script setup>
const props = defineProps({
  title: String
})
</script>

<template>
  <h3>{{ title || 'waiting for data...' }}</h3>
</template>