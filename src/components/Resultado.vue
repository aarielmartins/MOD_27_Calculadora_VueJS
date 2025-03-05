<script setup>
    const props = defineProps(['resultado'])
</script>

<template>
    <div class="row">
        <div class="col">
            <br>
            <h5>O resultado é</h5>
            <span class="d-flex justify-content-center">{{ props.resultado }}</span>
            <br>
        </div>
    </div>
</template>

<style scoped>
    span{
    font-size: 50px;
    color: #8282e6;
    font-weight: 500;
    }
</style>