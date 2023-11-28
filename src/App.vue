<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

// import CardsList from "./components/CardsList.vue";
export default {
  data() {
    return {
      store,
    };
  },
  created() {
    this.store.loading = true;
    axios.get(this.store.apiUrl).then((resp) => {
      this.store.cardsArray = resp.data.data;
      this.store.loading = false;
    });
  },
  // methods: {
  //   showSelected() {
  //     console.log("cerca");
  //     axios.get(this.store.apiUrl, {
  //       params: {
  //         archetype: this.store.archetypeChoice,
  //       },
  //     });
  //     // .then((resp) => {
  //     //   this.store.characters = resp.data.results;
  //     // });
  //   },
  // },
  // methods: {
  //   getCards: function() {
  //     axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php");
  //     params {
  //       num = 20,
  //       offset = 0,

  //     }

  //   },
  // },
  components: {
    AppHeader,
    AppMain,
  },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>
