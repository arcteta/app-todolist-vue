<script setup>
import ButtonDelete from './ButtonDelete.vue';

defineProps({ todos: { type: Array, required: true } })

</script>

<template>
    <div>
        <h1 style="color: white;"> LIST To do: </h1>
        <div class="grid-container" v-if="todos.length > 0">
            <div class="card" v-for="item of todos" v-bind:key="item.id">
                <div class="card-content">
                    <h2 class="todo-name">{{ item.todo }}</h2>
                    <h2 class="date-name" style="background-color: aqua;">{{ item.date }}</h2>
                    <ButtonDelete @on-click="$emit('remove', item.id)">delete</ButtonDelete>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 15px;
}

.card {
    background-color: white;
    padding: 16px 8px;
    border: 1px solid;
    box-shadow: 5px 10px;

}

.card-content {
    color: brown;
    display: flex;
    justify-content: space-between;
}

.card-content2 {
    background-color: brown;
    color: brown;
    display: flex;
    justify-content: space-between;
}

.btn-container {
    align-items: center;
    justify-items: center;
    padding: 8px;
}

h1 {
    font-family: 'Montserrat', sans-serif;
    margin-bottom: 1rem;
}

h2 {
    font-family: 'Montserrat', sans-serif;
    size: 20px;
}
</style>