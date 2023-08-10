<script setup>
import { ref, computed } from 'vue'

let id = 0

const newTodo = ref('')
const hideCompleted = ref(false)
const todos = ref([
  { id: id++, text: 'Learn HTML', done: true },
  { id: id++, text: 'Learn JavaScript', done: true },
  { id: id++, text: 'Learn Vue', done: false }
])

const filteredTodos = computed(() => {
  return hideCompleted.value
    ? todos.value.filter((t) => !t.done)
    : todos.value
})

function addTodo() {
  if (newTodo.value) {
    todos.value.push({ id: id++, text: newTodo.value, done: false })
    newTodo.value = ''
  }
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}
</script>

<template>
  <h2> Filtered Most Basic list ever 🐸🪐</h2>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>
  </form>
  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)" class="close-button">❌</button>
    </li>
  </ul>
</template>

<style scoped>
form {
  display: inline-block;
}

.done {
  text-decoration: line-through;
}

li {
  margin: 10px 0 10px 0;
}

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