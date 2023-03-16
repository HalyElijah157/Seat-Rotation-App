<script setup>
    import Seat from './Seat.vue'
    // const names=[
    //     'Elijah', 'Hannah', 'saige', 'lilli'
    // ]

    const people=[
        {
            name: 'Elijah',
            driver: true,
            booster: false,
        },
        {
            name: 'Hannah',
            driver: false,
            booster: false,
        },
        {
            name: 'Saige',
            driver: false,
            booster: false,
        },
        {
            name: 'Lilli',
            driver: false,
            booster: true,
        }
    ]

    const seats=[
        {
            driver: false,
            booster: false,
        },
        {
            driver: false,
            booster: false
        },
        {
            driver: false,
            booster: true
        },
        {
            driver: true,
            booster: false,
        },
        {
            driver: false,
            booster: false
        },
        {
            driver: false,
            booster: false
        }
    ]

    const randamize = () => {
        for (let person of people) {
            for (let seat of seats) {
                seat.passenger=person
            }
            //only one person per seat
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
        <Seat v-for="seat in seats" :seat="seat"/>
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