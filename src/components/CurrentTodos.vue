<template>
  <div id="current-todos" class="box">
    <h3>Current({{todos.length}})</h3>
    <table class="table">
      <thead>
        <tr>
          <th>Task</th>
          <th>Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="todo in todos">
          <td>{{todo.body}}</td>
          <td>
            <span class="control is-grouped">
              <button type="button" @click="edit(todo)" class="button is-primary">
                <span class="icon glyphicon-edit"><i class="fa fa-edit"></i></span>&nbsp;Edit
              </button>
              <button type="button" @click="complete(todo)" class="button is-info">
                <span class="icon glyphicon-edit"><i class="fa fa-check"></i></span>&nbsp;Complete
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
    edit(todo) {
      this.$store.dispatch('editTodo', todo);
    },
    complete(todo) {
      this.$store.dispatch('completeTodo', todo);
    },
    remove(todo) {
      this.$store.dispatch('removeTodo', todo);
    },
  },
  computed: {
    todos() {
      return this.$store.getters.todos;
    },
  },
};
</script>
<style>
  .btn-group {
    float: right;
  }
</style>
