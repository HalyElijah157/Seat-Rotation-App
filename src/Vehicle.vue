<script setup>
    import Seat from './components/Seat.vue'
</script>

<template>
    <div class="seatParent">
        <Seat />
        <Seat />
        <Seat />
        <Seat />
        <Seat />
        <Seat />
    </div>
</template>

<style scoped>
    .SeatParent {
        display: grid;
        grid-template-columns: 100px 50px 100px;
        grid-template-rows: 80px auto 80px; 
        column-gap: 10px;
        row-gap: 15px;
    }
</style>