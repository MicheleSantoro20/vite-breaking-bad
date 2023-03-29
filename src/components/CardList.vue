<script>
import {store} from '../store.js';

export default {
    name: "CardList",
    data() {
            return {
                store
            }
    },
    props : {
        image : String,
        name : String,
        archetipo : String
    }
}

</script>

<template>
        <div class="wrapper">
            <img  :src="image" alt="name">
            <h3>{{ name }}</h3>
            <h4>{{ archetipo }}</h4>
        </div>
</template>

<style scoped lang="scss">
    .wrapper {
        margin: 10px;
        width: calc(100% / 6);
        padding: 2px;
        text-align: center;
        background-color: #d48f38;
    }

    img {
        width: 100%;
    }

</style>