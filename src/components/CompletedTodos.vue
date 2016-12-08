<template>
  <div id="completed-todos" class="box">
    <h3 class="is-pulled-left">Completed({{completed.length}})</h3>
    <button class="button is-danger is-pulled-right" type="button" @click="removeAll()" :disabled="!completed.length">
      <span class="icon glyphicon-edit"><i class="fa fa-trash"></i></span>&nbsp;Clear all completed
    </button>
    <table class="table">
      <thead>
        <tr>
          <th>Task</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="todo in completed">
          <td>{{todo.body}}</td>
          <td>
            <span class="control is-grouped">
              <button type="button" @click="uncomplete(todo)" class="button is-warning">
                <span class="icon glyphicon-edit"><i class="fa fa-check"></i></span>&nbsp;Uncomplete
              </button>
              <button type="button" @click="remove(todo)" class="button is-danger">
                <span class="icon glyphicon-edit"><i class="fa fa-trash"></i></span>&nbsp;Remove
              </button>
            </span>
          </td>
        </tr>
      </tbody>
    </table>
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
