<template>
  <div id="app" class="container is-fluid">
    <section class="box hero">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">ToDoist</h1>
          <h2 class="subtitle">The ultimate ToDo App</h2>
        </div>
      </div>
    </section>
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
