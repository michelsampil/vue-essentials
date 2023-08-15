<script setup>
import HelloWorld from './components/HelloWorld.vue'
import CounterButton from './components/CounterButton.vue';
import TodoList from './components/TodoList.vue';
import FilteredTodoList from './components/FilteredTodoList.vue';
import FilteredTodosNoComputed from './components/FilteredTodosNoComputed.vue';
import DayNightSwitch from './components/DayNightSwitch.vue';
import Todo from './components/Todo.vue';
import List from './components/List.vue';
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  </header>
  <main>
    <div class="container">
      <HelloWorld />
    </div>
    <div class="container">
      <CounterButton />
    </div>
    <div class="container">
      <DayNightSwitch />
    </div>
    <div class="container">
      <TodoList />
    </div>
    <div class="container">
      <FilteredTodosNoComputed />
    </div>
    <div class="container">
      <FilteredTodoList />
    </div>
    <div class="fit-wrapper-group">
      <div class="container fit-wrapper">
        <Todo />
      </div>
      <div class="container fit-wrapper">
        <Todo />
      </div>
      <div class="container fit-wrapper">
        <Todo />
      </div>
    </div>
    <div class="container">
      <List />
    </div>
  </main>
</template>

<style>
.fit-wrapper-group {
  display: flex;
}

.container {
  padding: 10px;
  margin: 20px 0 20px 0;
  box-shadow: 0 0 10px #02AAB0;
  border-radius: 5px;
}

.fit-wrapper {
  width: fit-content;
  padding: 20px;
  margin: 0px 5px 0px 5px;
}
</style>

