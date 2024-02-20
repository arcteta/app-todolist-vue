<script setup>
import TodoBoard from './components/TodoBoard.vue';
import { ref } from 'vue';

const todos = ref([])

function add(data){
    todos.value.push({id: crypto.randomUUID(), todo: data.todo})
    data.clear()
}
</script>

<template>
    <section class="wrapper">
        <TodoBoard @addTodo="add" />
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