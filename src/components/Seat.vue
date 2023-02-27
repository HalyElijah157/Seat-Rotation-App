<script setup>
    const props = defineProps(['name'])
</script>

<template>
    <div class="container">
        <img src="carSeat.png" class="seat">
        <div class="centered">{{ props.name }}</div>
    </div>
</template>

<style scoped>
    .container {
        position: relative;
        display: flex;
        justify-content: center;
    }
    .centered {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
</style>