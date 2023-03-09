<script setup>
    import Seat from './Seat.vue'
    // const names=[
    //     'Elijah', 'Hannah', 'saige', 'lilli'
    // ]

    const people=[
        {
            name: 'Elijah',
            driver: true,
            bosterSeat: false,
        },
        {
            name: 'Hannah',
            driver: false,
            bosterSeat: false,
        },
        {
            name: 'Saige',
            driver: false,
            bosterSeat: false,
        },
        {
            name: 'Lilli',
            driver: false,
            bosterSeat: false,
        }
    ]

    const seats=[
        {
            driver: true,
            bosterSeat: false,
        },
        {
            driver: false,
            bosterSeat: false
        },
        {
            driver: false,
            bosterSeat: false
        },
        {
            driver: true,
            bosterSeat: false,
        },
        {
            driver: false,
            bosterSeat: false
        },
        {
            driver: false,
            bosterSeat: false
        }
    ]

    const randamize = () => {
        for (let seat of seats) {
            seat.passenger={name: 'Elijah'} 
            //only aplise passenger if the person meets aqwierments
        }
    }

    randamize()
    console.log(seats)
</script>

<template>
    <div class="seatParent">
        <!-- <Seat v-for="name in names" :name="name"/> -->
        <!-- <Seat v-for="person in people" :person="person"/> -->
        <Seat v-for="seat in seats" :person="seat.passenger"/>
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