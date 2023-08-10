<script setup>
import HelloWorld from './components/HelloWorld.vue'
import CounterButton from './components/CounterButton.vue';
import TodoList from './components/TodoList.vue';
import FilteredTodoList from './components/FilteredTodoList.vue';
import FilteredTodosNoComputed from './components/FilteredTodosNoComputed.vue';
import DayNightSwitch from './components/DayNightSwitch.vue';
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

  </main>
</template>

<style>
.container {
  padding: 10px;
  margin: 20px 0 20px 0;
  box-shadow: 0 0 10px #02AAB0;
  border-radius: 5px;
}
</style>

