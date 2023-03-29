<script>
import axios from 'axios';
import { store } from './store.js';
import MainPage from './components/MainPage.vue';

export default {
    components : {
      MainPage,
    },
    data () {
      return {
        store
      }
    },
    methods: {
      getCard() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
        .then(response => {
          this.store.charactersList = response.data.data;
        })
      }
    },
    created() {
      this.getCard();
      console.log(this.store);
    }
}




</script>

<template>

</template>

<style scoped lang="scss">
  @use "./styles/general.scss";
</style>
