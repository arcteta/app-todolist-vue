<script setup>
import ButtonDelete from './ButtonDelete.vue';

 defineProps({ todos: { type: Array, required: true } })

</script>

<template>
    <div>
        <h1> LIST To do: </h1>
        <div class="grid-container" v-if="todos.length > 0">
            <div class="card" v-for="item of todos" v-bind:key="item.id">
                <div class="card-content">
                    <h2>{{ item.todo }}</h2>
                    <ButtonDelete @on-click="$emit('remove',item.id)">delete</ButtonDelete>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 8px;
}

.card {
    background-color: white;
    padding: 16px 8px;
    border-radius: 8px;

}

.card-content {
    color: brown ;
    display: flex;
    justify-content: space-between;
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