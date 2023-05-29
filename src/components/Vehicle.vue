<script setup>
    import Seat from './Seat.vue'

    const people=[
        {
            name: 'Adam',
            driver: true,
            booster: false,
        },
        {
            name: 'Jennifer',
            driver: true,
            booster: false,
        },
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
            booster: false,
        }
    ]

    function addPeople() {
        var names = document.getElementById("myText").value;
        console.log(names)
    }

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
            booster: false
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
        const driverSeatIndex=seats.findIndex(seat=>{
            return seat.driver && seat.driver===true
        })
        const drivers = people.filter(person=>{
            return person.driver && person.driver===true
        })

        const randomDriverindex = Math.floor(Math.random() * drivers.length)

        seats[driverSeatIndex].passenger=drivers[randomDriverindex]
        drivers[randomDriverindex].seated=true
        const passengers = people.filter(person=>{
            return drivers[randomDriverindex].name !== person.name
        })

        for (let person of passengers) {
            let count = 0
            while (!person.seated){
                const randomIndex = Math.floor(Math.random() * seats.length)
                const seat = seats[randomIndex]
                count++
                if(seat.passenger){
                    continue
                }
                console.log('person',JSON.stringify(person,null,2))
                console.log('seats',JSON.stringify(seats[randomIndex],null,2))
                seats[randomIndex].passenger=person
                person.seated=true
                if (count > 10){
                    break
                }
            }
        }
    }

    const dropdowntest = () => {
        const x = document.getElementById('myul')
        console.log(x.value)
    }
</script>

<template>
    <div class="seatParent">
        <Seat v-for="seat in seats" :seat="seat"/>
    </div>

    <ul id="myul">
        <li value="dad">Adam</li>
        <li value="mom">Jennifer</li>
        <li value="brother">Elijah</li>
        <li value="sisterOne">Hannah</li>
        <li value="sisterTwo">Saige</li>
        <li value="sisterThree">Lilli</li>
    </ul>

    <input type="text" id="peopleTextBox" value="Add People">

    <button onclick="addPeople()">add people</button>

    <button type="button" id="mybtn" @click="randamize">button</button>
</template>

<style scoped>
    .seatParent {
        display: grid;
        grid-template-columns: [c1] auto [column2] auto [column3] auto [end];
        grid-template-rows: [row1] auto [row2] auto [row3] auto [end];
        column-gap: 10px;
        row-gap: 15px;
    }
</style>