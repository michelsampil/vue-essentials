<script>
let id = 0

export default {
  data() {
    return {
      newTodo: '',
      hideCompleted: false,
      todos: [
        { id: id++, text: 'Learn HTML', done: true },
        { id: id++, text: 'Learn JavaScript', done: true },
        { id: id++, text: 'Learn Vue', done: false }
      ],
      filteredTodos: [
        { id: id++, text: 'Learn HTML', done: true },
        { id: id++, text: 'Learn JavaScript', done: true },
        { id: id++, text: 'Learn Vue', done: false }
      ]
    }
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo, done: false })
      this.newTodo = ''
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo)
    },
    filterTodos() {
      this.hideCompleted = !this.hideCompleted;
      console.log('hideCompleted', this.hideCompleted);
      if (this.hideCompleted) {
        this.filteredTodos = this.todos.filter((t) => !t.done);
      } else {
        this.filteredTodos = this.todos;
      }
    }
  }
}
</script>

<template>
  <h2> Filtered Most Basic list ever 🐸🪐 (No computed)</h2>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>
  </form>
  <button @click="filterTodos">
    {{ this.hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)" class=".close-button">❌</button>
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