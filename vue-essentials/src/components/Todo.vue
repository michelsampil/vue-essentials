<script setup>
import { ref } from 'vue';
import Card from './Card.vue';
import LoadingSpinner from './LoadingSpinner.vue';
let todoId = ref(1)
let isLoading = ref(true);
const todoData = ref(null)

async function fetchData() {
  isLoading.value = true;
  setTimeout(async () => {
    todoData.value = null
    console.log(todoId)
    const res = await fetch(
      `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
    )
    todoData.value = await res.json()
    todoId.value++;
    isLoading.value = false;
  }, 2000);
}

fetchData()
</script>

<template>
  <h2>Todo List </h2>
  <br />
  <Card>
    <LoadingSpinner v-if="isLoading" />
    <div v-else="!isLoading">
      <h2>{{ `TodoId: ${todoId}` }}</h2>
      <br />
      <p>{{ `UserId: ${todoData.UserId}` }}</p>
      <p>{{ `Title: ${todoData.title}` }}</p>
      <p>{{ `Completed: ${todoData.completed}` }}</p>
    </div>
  </Card>
  <button @click="fetchData">Fetch next todo</button>
</template>

<style scope>
button {
  background-image: linear-gradient(to right, #02AAB0 0%, #00CDAC 51%, #02AAB0 100%);
  margin: 10px;
  padding: 15px 45px;
  text-align: center;
  text-transform: uppercase;
  transition: 0.5s;
  background-size: 200% auto;
  color: white;
  box-shadow: 0 0 20px #eee;
  border-radius: 10px;
}

.close-button {
  padding: 5px;
}

button:hover {
  background-position: right center;
  color: #fff;
  text-decoration: none;
}
</style>