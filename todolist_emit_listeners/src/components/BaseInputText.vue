<!--
 * @Author: Gaiwa 13012265332@163.com
 * @Date: 2023-10-26 18:42:18
 * @LastEditors: Gaiwa 13012265332@163.com
 * @LastEditTime: 2023-10-26 20:21:29
 * @FilePath: \todolist\src\components\BaseInputText.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div>
    <input
      type="text"
      :class="['todo-input', { active: isActive }]"
      :value="value"
      v-on="listeners"
      @focus="isActive = true"
      @blur="isActive = false"
    />
  </div>
</template>

<script>
export default {
  name: "BaseInputText",
  props: {
    value: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      isActive: false,
    };
  },
  computed: {
    listeners() {
      return {
        ...this.$listeners, //将原本的事件混入到自己添加的事件中
        input: (event) => this.$emit("input", event.target.value),
      };
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