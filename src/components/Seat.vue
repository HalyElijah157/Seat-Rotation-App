<script setup>
    const props = defineProps(['seat'])
</script>

<template>
    <div class="container">
        <img src="carSeat.png" class="seat">
        <div class="centered">{{ props.seat.passenger.name }}</div>
        <div v-if="props.seat.driver" class="underline">Driver</div>
        <div v-if="props.seat.booster" class="underline">Booster</div>
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
        top: 40%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    .underline {
        position: absolute;
        top: 60%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
</style>