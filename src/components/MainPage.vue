<script>
import CardList from './CardList.vue';
import {store} from '../store.js';


    export default {
        name: "MainPage",
        components : {
            CardList,
        },
        data() {
            return {
                store
            }
        }
    }

</script>



<template>
    <CardList v-for="(card, index) in store.charactersList" :image="card.card_images[0].image_url" :name="card.name" :key="index"/>
</template>



<style>

</style>