<script setup>
import TodoBoard from './components/TodoBoard.vue';
import TodoList from './components/TodoList.vue';
import { ref } from 'vue';

const todos = ref([])

function add(data) {
    todos.value.push({ id: crypto.randomUUID(), todo: data.todo })
    data.clear()

    console.log(data);
}

function remove(id){
    todos.value = todos.value.filter(item => item.id !== id)
}
</script>

<template>
    <section class="wrapper">
        <TodoBoard @addTodo="add" />
        <TodoList :todos="todos" @remove="remove"/>
    </section>
</template>


<style scoped>
.wrapper {
    background-color: #ED7D31;
    display: flex;
    flex-direction: column;
    height: 100svh;
    justify-content: center;
    align-items: center;
}
</style>