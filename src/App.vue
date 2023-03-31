<script>
import axios from 'axios';
import { store } from './store.js';
import MainPage from './components/MainPage.vue';
import TheHeader from './components/TheHeader.vue'
import Loading from './components/Loading.vue';
import FilterBar from './components/FilterBar.vue';

export default {
    components : {
      MainPage,
      TheHeader,
      Loading,
      FilterBar
    },
    data () {
      return {
        store
      }
    },
    methods: {
      getCard() {

        let Api ="https://db.ygoprodeck.com/api/v7/cardinfo.php"

        if (this.store.filter.length > 0) {
          Api += `?archetype=${this.store.filter}`;

        }
        axios.get(Api)
        .then(response => {
          this.store.charactersList = response.data.data;
          this.store.loading = false;
        })
        console.log(this.store.filter)

      },

    },
    created() {
      console.log(this.store);
    },
}

</script>

<template>

  <TheHeader />
  <Loading />
  <FilterBar @filtro="getCard" />
  <MainPage />


</template>





<style lang="scss">
  @use "./styles/general.scss";
</style>
