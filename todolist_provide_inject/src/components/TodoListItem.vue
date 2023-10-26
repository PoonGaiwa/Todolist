<template>
  <ul class="todo-list--ul">
    <li
      class="todo-list--item"
      :key="todo.id"
      :todo="todo"
      v-for="todo in todos"
    >
      {{ todo.text }}
      <button class="todo-button--clean" @click="remove(todo.id)">x</button>
    </li>
  </ul>
</template>

<script>
export default {
  name: "TodoListItem",
  inject: ["newTodoText", "todos"],
  data() {
    return {};
  },
  methods: {
    remove(id) {
      this.todos = this.todos.filter((todo) => {
        return todo.id !== id;
      });
    },
  },
};
</script>

<style>
</style>