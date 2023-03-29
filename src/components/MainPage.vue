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
    <main>
        <div class="container">
            <CardList v-for="(card, index) in store.charactersList" :image="card.card_images[0].image_url" :name="card.name" :archetipo="card.archetype" :key="index"/>
        </div>
    </main>


</template>



<style scoped lang="scss">

*  {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
.container {

    width: 1200px;
    margin: 80px auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    background-color: white;
}
main {
    padding: 30px;
    background-color: #d48f38;
}
</style>