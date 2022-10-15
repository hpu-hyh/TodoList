<template>
  <main>
    <div class="container">
      <h1>欢迎使用EVA待办事项!</h1>
      <TodoAdd :tid="todos.length" @add-todo="addTodo"></TodoAdd>
      <TodoFilter :selected="filter" @change-filter="filter = $event"></TodoFilter>
      <TodoList :todos="filteredTodos"></TodoList>
    </div>
  </main>
</template>

<script>
import { computed, ref } from 'vue'
import TodoAdd from "./components/TodoAdd.vue"
import TodoFilter from "./components/TodoFilter.vue"
import TodoList from "./components/TodoList.vue"
export default {
  name: 'App',
  components: {
    TodoAdd,
    TodoFilter,
    TodoList
  },
  setup() {
    const todos = ref([]);
    const addTodo = (todo) => todos.value.push(todo);

    const filter = ref("all");
    const filteredTodos = computed(() => {
      switch (filter.value) {
        case "done":
          return todos.value.filter((todo) => todo.completed);
        case "todo":
          return todos.value.filter((todo) => !todo.completed);
        default:
          return todos.value;
      }
    })

    return {
      todos,
      addTodo,
      filter,
      filteredTodos
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Helvetica, sans-serif;
}

/* all of page */
main {
  width: 100vw;
  min-height: 100vh;
  display: grid;
  align-items: center;
  justify-content: center;
  background: url(../public/bgc.jpg) no-repeat;
  background-size: cover;
}

.container {
  width: 60%;
  min-width: 400px;
  box-shadow: 0 0 24px rgba(0, 0, 0, 0.15);
  border-radius: 24px;
  padding: 48px 28px;
  background-color: rgb(118, 68, 45);
}

/* title */
h1 {
  margin: 24px 25px;
  font-size: 28px;
  color: rgb(51, 65, 66);
}
</style>
