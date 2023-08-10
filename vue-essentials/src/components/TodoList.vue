<script setup>
import { ref } from 'vue'
let id = 0
const newTodo = ref('')
const todos = ref([])

function addTodo() {
  if (newTodo.value) {
    todos.value.push({ id: id++, text: newTodo.value })
    newTodo.value = ''
  }
}
function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}
</script>

<template>
  <h2> Most Basic list ever 🐸🪐</h2>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button> ➕ Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)" class="close-button"> ❌ </button>
    </li>
  </ul>
</template>

<style scoped>
input {
  font-size: medium;
  padding: 15px 45px;
}

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