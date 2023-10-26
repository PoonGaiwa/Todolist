<!--
 * @Author: Gaiwa 13012265332@163.com
 * @Date: 2023-10-26 18:42:18
 * @LastEditors: Gaiwa 13012265332@163.com
 * @LastEditTime: 2023-10-26 21:25:08
 * @FilePath: \todolist\src\components\BaseInputText.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div>
    <input
      type="text"
      :class="['todo-input', { active: isActive }]"
      v-model="value"
      @keydown.enter="addTodo"
      @focus="isActive = true"
      @blur="isActive = false"
    />
  </div>
</template>

<script>
export default {
  name: "BaseInputText",
  inject: ["newTodoText", "todos", "todoIndex"],
  data() {
    return {
      value: "",
      isActive: false,
    };
  },
  methods: {
    addTodo() {
      this.newTodoText = this.value.trim();
      if (this.newTodoText !== "") {
        this.todos.push({
          id: this.todoIndex++,
          text: this.newTodoText,
        });
      }
      this.value = "";
      this.newTodoText = "";
    },
  },
};
</script>

<style>
.todo-input {
  padding-left: 8px;
  width: 80%;
  background-color: rgba(0, 0, 0, 0.2);
  line-height: 48px;
  border: 0;
  outline: 0;
  border-radius: 4px;
  color: #fff;
}
.active {
  box-shadow: 0 0 2px #000;
}
</style> 