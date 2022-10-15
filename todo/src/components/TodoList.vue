<template>
    <div class="todo-list">
        <TodoListItem v-for="todo in todos" :key="todo.id" :todo-item="todo"
            @change-state="todo.completed = $event.target.checked">
        </TodoListItem>
    </div>
</template>
<script>
import { defineComponent } from 'vue'
import TodoListItem from "./TodoListItem.vue"
export default defineComponent({
    name: 'TodoList',
    components: { TodoListItem },
    props: ["todos"],
})
</script>
<style  scoped>
.todo-list {
    display: grid;
    row-gap: 14px;
}
</style>