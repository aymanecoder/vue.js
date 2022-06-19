<template>
    <div class="grid">
        <div class="col-12 md:col-6 lg:col-3" v-for="pet in pets" :key="pet.id">
            <!-- <h3>{{pet.name}}</h3> -->
            <Pet @remove-pet="$emit('remove-pet',pet.id)" @add-favorite="$emit('add-favorite',pet.id)" :pet="pet" />

        </div>
    </div>
</template>

<script>
import Pet from '../components/Pet'
export default {
    props: {
        pets: Array
    },
    components: {
        Pet
    },
    emits:["remove-pet","add-favorite"],

}
</script>

<style>
</style>