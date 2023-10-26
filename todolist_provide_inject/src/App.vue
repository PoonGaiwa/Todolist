<template>
  <div id="app">
    <h1>每日清单</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
export default {
  name: 'App',
  components: {
    TodoList
  }
}
</script>

<style>
*,
*::after,
*::before{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  background-color: rgba(122,122,122,.4);
}
#app{
  margin: 30px auto;
  max-width: 560px;
  padding: 40px;
  text-align: center;
  border: 1px solid #fff;
}
h1 {
  padding: 24px 0;
}
</style>
