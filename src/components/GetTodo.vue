<template>
  <div id="get-todo" class="container">
    <h1>What do you need To Do today?</h1>
    <form  class="input-group">
      <input type="text" class="form-control" :value="newTodo" @change="getTodo" placeholder="I need to...">
      <span class="input-group-btn">
        <button type="submit" class="btn btn-primary" @click="addTodo">Add Todo</button>
      </span>
    </form>
  </div>
</template>
<script>
  export default {
    methods: {
      getTodo(e) {
        this.$store.dispatch('getTodo', e.target.value);
      },
      addTodo(e) {
        e.preventDefault();
        this.$store.dispatch('addTodo');
        this.$store.dispatch('clearTodo');
      },
    },
    computed: {
      newTodo() {
        return this.$store.getters.newTodo;
      },
    },
  };
</script>
