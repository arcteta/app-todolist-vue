r<script setup>
import { ref } from 'vue';

const todo = ref("")

function clear(){
    todo.value = ''
}
</script>

<template>
    <h1 class="title">-= MY TODO =-</h1>
    <form @:submit.prevent="$emit('addTodo',{ todo , clear })">
        <div class="form-control">
            <label for="todo">todo :</label>
            <input type="text" v-model="todo" id="todo" placeholder="todo task" required>
        </div>
        <div style="text-align: end;">
            <button class="btn-add">add</button>
        </div>
    </form>
</template>


<style scoped>
.title {
    font-family: 'Montserrat', sans-serif;
    color: #F6F1EE;
    font-size: 1.5rem;
    text-align: center;
    margin-bottom: 2rem;
}

.form-control {
    margin-bottom: 1rem;
}

.form-control label {
    font-family: 'montserrat', sans-serif;
    margin-right: 1rem;
    color: #F6F1EE;
}

.btn-add {
    font-family: 'Montserrat', sans-serif;
    color: #F6F1EE;
    background-color: #4F4A45;
}
</style>