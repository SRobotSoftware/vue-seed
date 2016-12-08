<template>
  <div id="app" class="container is-fluid">
    <TitleHero></TitleHero>
    <GetTodo></GetTodo>
    <CurrentTodos></CurrentTodos>
    <CompletedTodos></CompletedTodos>
  </div>
</template>

<script>
import TitleHero from './components/TitleHero.vue';
import GetTodo from './components/GetTodo.vue';
import CurrentTodos from './components/CurrentTodos.vue';
import CompletedTodos from './components/CompletedTodos.vue';

export default {
  name: 'app',
  components: {
    TitleHero,
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
