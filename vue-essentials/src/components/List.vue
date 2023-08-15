<script setup>
import { ref } from 'vue'
import ListItem from './ListItem.vue'

const newCardTitles = ref(['I like 🥑', 'I love 🥔', `I'm from 🪐`]);
</script>

<template>
  <h1> Happy List 😛</h1>
  <ListItem v-for="cardTitle in newCardTitles" :key="cardTitle" :title="cardTitle" />
</template>
