<!--
 * @Author: Gaiwa 13012265332@163.com
 * @Date: 2023-10-26 19:09:06
 * @LastEditors: Gaiwa 13012265332@163.com
 * @LastEditTime: 2023-10-26 21:15:15
 * @FilePath: \todolist\src\components\TodoList.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div class="todo-list">
    <BaseInputText />
    <div v-show="todos.length > 0">
      <h2 class="todo-list--title">待完成任务</h2>
      <TodoListItemVue />
    </div>
  </div>
</template>

<script>
import BaseInputText from "./BaseInputText";
import TodoListItemVue from "./TodoListItem.vue";
export default {
  name: "TodoList",
  components: {
    BaseInputText,
    TodoListItemVue,
  },
  data() {
    return {
      newTodoText: "",
      todos: [],
      todoIndex: 1,
    };
  },
  provide() {
    return {
      newTodoText: this.newTodoText,
      todos: this.todos,
      todoIndex: this.todoIndex,
    };
  },
};
</script>

<style>
.todo-list {
  margin-top: 10px;
  padding: 8px;
}
.todo-list--title {
  margin-top: 10px;
  padding: 10px;
  font-size: 18px;
  font-weight: 700;
  color: black;
  text-align: left;
}
.todo-list--ul {
  padding-left: 18px;
  list-style: none;
  text-align: left;
}
.todo-list--item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 4px;
  padding: 0 10px;
  height: 45px;
  background-color: #fff;
  font-size: 14px;
  border-radius: 8px;
}
.todo-button--clean {
  width: 40px;
  height: 28px;
  border: 0;
  color: #fff;
  background-color: rgba(0, 0, 0, 0.3);
  border-radius: 4px;
  cursor: pointer;
}
.todo-button--clean:hover {
  background-color: rgba(0, 0, 0, 0.6);
  color: #ccc;
}
</style>