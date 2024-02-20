<template>
    <button class="btn-del" @click="$emit('onClick')">
        <slot />
    </button>
</template>


<style scoped>
.btn-del {
    font-family: 'Monserrat', sans-serif;
    width: auto;
    color: #F6F1EE;
    background-color: #4F4A45;
    border-radius: 8px;
}
</style>