<script>
import axios from "axios";
import { store } from "../store";
import CardsList from "./CardsList.vue";
import CardsStats from "./CardsStats.vue";
import AppLoader from "./AppLoader.vue";
import AppSearch from "./AppSearch.vue";
import ChangePage from "./ChangePage.vue";

export default {
  data() {
    return {
      store,
      axios,
      page: 643,
    };
  },
  components: {
    CardsList,
    CardsStats,
    AppLoader,
    AppSearch,
    AppSearch,
    ChangePage,
    ChangePage,
  },
  created() {
    // Get all card
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?").then((resp) => {
      this.store.allCardsArray = resp.data.data;
      console.log(this.store.allCardsArray.length / 20);
    });
  },
  methods: {
    loadPage() {
      axios
        .get(this.store.apiUrl, {
          params: {
            num: 20,
            offset: this.page * 20,
          },
        })
        .then((resp) => {
          this.store.cardsArray = resp.data.data;
        });
    },

    showSelected() {
      if (this.store.archetypeChoice == "") {
        this.loadPage();
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

    showPrevPage() {
      console.log("ciao");
      if (this.page == 0) return;
      this.page--;
      this.loadPage();
    },
    showNextPage() {
      if (this.page == Math.floor(this.store.allCardsArray.length / 20)) return;
      this.page++;
      this.loadPage();
    },
  },
};
</script>

<template>
  <div class="main px-5 pt-5">
    <AppLoader v-if="store.loading == true" />
    <div class="container p-5" v-else>
      <h6 class="text-end mt-5">Current Page: {{ page }}</h6>
      <AppSearch @cardChoice="showSelected" />
      <ChangePage @prevPage="showPrevPage" @nextPage="showNextPage" />
      <CardsStats />
      <CardsList />
      <ChangePage @prevPage="showPrevPage" @nextPage="showNextPage" />
      <h6 class="text-end mt-5">Current Page: {{ page }}</h6>
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
