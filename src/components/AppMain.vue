<script>
import axios from "axios";
import { store } from "../store";
import CardsList from "./CardsList.vue";
import CardsStats from "./CardsStats.vue";
import AppLoader from "./AppLoader.vue";
import AppSearch from "./AppSearch.vue";
export default {
  data() {
    return {
      store,
      axios,
    };
  },
  components: {
    CardsList,
    CardsStats,
    AppLoader,
    AppSearch,
    AppSearch,
  },
  methods: {
    showSelected() {
      console.log("select");
      if (this.store.archetypeChoice == "") {
        axios.get(this.store.apiUrl).then((resp) => {
          this.store.cardsArray = resp.data.data;
        });
      } else {
        axios
          .get(this.store.apiUrl, {
            params: {
              num: 20,
              offset: 0,
              archetype: this.store.archetypeChoice,
            },
          })
          .then((resp) => {
            this.store.cardsArray = resp.data.data;
          });
      }
    },
  },
};
</script>

<template>
  <div class="main px-5 pt-5">
    <AppLoader v-if="store.loading == true" />
    <div class="container p-5" v-else>
      <AppSearch @cardChoice="showSelected" />
      <CardsStats />
      <CardsList />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.main {
  background-color: $mainColor;
  min-height: 90vh;

  .container {
    background-color: white;
  }
}
</style>
