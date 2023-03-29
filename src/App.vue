<script>
import axios from 'axios';
import { store } from './store.js';
import MainPage from './components/MainPage.vue';
import TheHeader from './components/TheHeader.vue'

export default {
    components : {
      MainPage,
      TheHeader,
    },
    data () {
      return {
        store
      }
    },
    methods: {
      getCard() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Alien')
        .then(response => {
          this.store.charactersList = response.data.data;
          this.store.loading = false;
        })
      },

    },
    created() {
      this.getCard();
      console.log(this.store);
    }
}

</script>

<template>
  <TheHeader />
  <MainPage />
</template>





<style lang="scss">
  @use "./styles/general.scss";
</style>
