<template>
  <li class="todo-list--item">
    {{ todo.text }}
    <button class="todo-button--clean" @click="cleanTask(todo.id)">x</button>
  </li>
</template>

<script>
export default {
  name: "TodoListItem",
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {};
  },
  methods: {
    cleanTask(id) {
      this.$emit("remove", id);
    },
  },
};
</script>

<style>
</style>