<script>
    import {store} from '../store.js';

    export default {
        name: "FilterBar",
        data() {
            return {
                store
            }
        }
    }

</script>


<template>

    <div class="bg-color">
        <select @change="$emit('filtro')" v-model="store.filter" id="filter" class="text">
            <option value="alien">Alien</option>
            <option value="blue-eyes">Blue-Eyes</option>
            <option value="synchron">Synchron</option>
            <option value="Archfiend">Archfiend</option>
            <option value="Umi">Umi</option>
            <option value="ABC">ABC</option>
        </select>
    </div>


</template>


<style scoped lang="scss">

.bg-color {
    background-color: #d48f38;
    padding: 30px;
}

.text {
    font-size: 20px;
    padding: 5px;
    border: none;
    border-radius: 10px;
    background-color: #845EC2;
}

</style>