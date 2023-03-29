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
        name : String
    }
}

</script>

<template>
    <div class="container">
        <div class="wrapper">
            <img :src="image" alt="name">
            <h3>{{ name }}</h3>
        </div>
    </div>

</template>

<style scoped lang="scss">
    .wrapper {
        width: 1200px;
        margin: auto;
    }
</style>