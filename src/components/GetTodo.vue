<template>
  <div id="get-todo" class="box">
    <h1>What do you need To Do today?</h1>
    <form>
      <span class="control has-addons">
        <input type="text" class="input is-primary" :value="newTodo" @change="getTodo" placeholder="I need to...">
        <button type="submit" class="button is-primary" @click="addTodo">Add Todo</button>
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
