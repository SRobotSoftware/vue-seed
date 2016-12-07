<template>
  <div id="completed-todos">
    <h3 v-if="completed.length">Completed({{completed.length}})</h3>
    <ul class="list-group">
      <li class="list-group-item" v-for="todo in completed">
      {{todo.body}}
      <button type="button" @click="remove(todo)" class="btn btn-default btn-sm"></button>
      <span class="glyphicon glyphicon-remove-circle"></span>&nbsp;Remove
      </li>
    </ul>
  </div>
</template>
<script>
  export default {
    methods: {
      remove(todo) {
        this.$store.dispatch('removeTodo', todo);
      },
    },
    computed: {
      completed() {
        return this.$store.getters.completedTodos;
      },
    },
  };
</script>
