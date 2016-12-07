<template>
  <div id="app">
    <CompletedTodos></CompletedTodos>
    <GetTodo></GetTodo>
    <CurrentTodos></CurrentTodos>
  </div>
</template>

<script>
import GetTodo from './components/GetTodo.vue';
import CurrentTodos from './components/CurrentTodos.vue';
import CompletedTodos from './components/CompletedTodos.vue';

export default {
  name: 'app',
  components: {
    GetTodo,
    CurrentTodos,
    CompletedTodos,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}
</style>
