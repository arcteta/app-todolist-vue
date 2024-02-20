<script setup>
import ButtonDelete from './ButtonDelete.vue';

</script>

<template>
    <div>
        <h1> LIST todo </h1>

        <div class="grid-container">
            <div class="card">
                <div class="card-content">
                    <h2>this is card content</h2>
                    <ButtonDelete>
                        delete
                    </ButtonDelete>
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

.card{
    
}
</style>