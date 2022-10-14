<template>
    <div class="input-add">
        <input type="text" name="todo" v-model="todoContent" @keyup.enter="emitAddTodo">
        <button @click="emitAddTodo">
            <i class="plus"></i>
        </button>
    </div>
</template>
<script>
import { defineComponent, ref } from 'vue'
export default defineComponent({
    name: 'TodoAdd',
    setup(props, context) {
        const todoContent = ref("");

        const emitAddTodo = () => {
            const todo = {
                id: props.tid,
                content: todoContent.value,
                completed: false,
            }
            context.emit("add-todo", todo);
            todoContent.value = "";
        }

        return {
            todoContent,
            emitAddTodo
        }
    }
})
</script>
<style  scoped>
.input-add {
    position: relative;
    display: flex;
    align-items: center;
}

.input-add input {
    padding: 26px 52px 16px 18px;
    border-radius: 48px;
    border: none;
    outline: none;
    box-shadow: 0 0 24px rgba(0, 0, 0, 0.08);
    width: 100%;
    font-size: 16px;
    color: #626262;
}

.input-add button {
    width: 46px;
    height: 46px;
    border-radius: 50%;
    background: rgb(118, 68, 45);
    border: none;
    outline: none;

    color: white;
    position: absolute;
    right: 0px;

    cursor: pointer;
}

/* 加号 */
.input-add .plus {
    display: block;
    width: 100%;
    height: 100%;
    background: linear-gradient(#fff, #fff), linear-gradient(#fff, #fff);
    background-size: 50% 3px, 3px 50%;
    background-position: center;
    background-repeat: no-repeat;
}
</style>