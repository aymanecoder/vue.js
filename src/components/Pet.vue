<template>
    <div class="pet">
        <!-- <h3>{{ pet.name }}</h3> -->
        <!-- <Button label="Save" /> -->
        <Card>
            <template #header>
                <img :src="pet.url" />
            </template>
            <template #title>
                {{ pet.name }}
            </template>
            <template #subtitle>
                Age: {{ pet.age }}
            </template>
            <!-- <template #content>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore sed consequuntur error
                    repudiandae numquam deserunt
                    quisquam repellat libero asperiores earum nam nobis, culpa ratione quam perferendis esse, cupiditate
                    neque quas!</p>
            </template> -->
            <template #footer>

                <Button @click="OnRemove(pet.id)"   icon="pi pi-times" label="Remove" class="p-button-danger" style="margin-right: 4em" />
                <Button @click="$emit('add-favorite',pet.id)" icon="pi pi-heart"
                    :class="[pet.isFavorite ? '' : 'p-button-outlined', 'p-button-rounded', 'p-button-danger']" />

            </template>
        </Card>
    </div>
</template>


<script>
export default {
    props:
    {

        pet: Object,
    },
    methods:{
        OnRemove(id){
           this.$emit("remove-pet",id);

        }
    }
}

</script>
<style>
</style>