<script setup>
    import Seat from './Seat.vue'
</script>

<template>
    <div class="seatParent">
        <Seat />
        <Seat />
        <Seat />
        <Seat />
        <Seat />
        <Seat />
        <Seat />
        <Seat />
    </div>
</template>

<style scoped>
    .seatParent {
        /* display: flex; */
        display: grid;
        grid-template-columns: [c1] auto [column2] auto [column3] auto [end];
        grid-template-rows: [row1] auto [row2] auto [row3] auto [end];
        column-gap: 10px;
        row-gap: 15px;
    }
</style>