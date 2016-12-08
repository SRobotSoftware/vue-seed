<template>
  <div id="app" class="container is-fluid">
    <GetTodo></GetTodo>
    <CurrentTodos></CurrentTodos>
    <CompletedTodos></CompletedTodos>
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
    margin-top: 25px;
  }
</style>
