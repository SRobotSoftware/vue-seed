<template>
  <div id="completed-todos" class="container">
    <h3>Completed({{completed.length}})</h3>
    <ul class="list-group">
      <li v-if="completed.length" class="list-group-item clearfix">
        <button class="btn btn-danger btn-sm pull-right" type="button" @click="removeAll()">
          <span class="glyphicon glyphicon-remove-circle"></span>&nbsp;Clear all completed
        </button>
      </li>
      <li class="list-group-item clearfix" v-for="todo in completed">
        <s>{{todo.body}}</s>
        <div class="btn-group pull-right">
          <button type="button" @click="uncomplete(todo)" class="btn btn-default btn-sm">
            <span class="glyphicon glyphicon-remove-circle"></span>&nbsp;Uncomplete
          </button>
          <button type="button" @click="remove(todo)" class="btn btn-default btn-sm">
            <span class="glyphicon glyphicon-remove-circle"></span>&nbsp;Remove
          </button>
        </div>
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
      removeAll() {
        this.$store.dispatch('removeCompletedTodos');
      },
      uncomplete(todo) {
        this.$store.dispatch('completeTodo', todo);
      },
    },
    computed: {
      completed() {
        return this.$store.getters.completedTodos;
      },
    },
  };
</script>
