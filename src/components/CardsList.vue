<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppCard,
  },
};
</script>

<template>
  <div class="row p-0 m-0 justify-content-between align-items-stretch">
    <div class="col-2 p-0 mx-2 mb-4" v-for="cardObj in store.cardsArray">
      <AppCard :card="cardObj" :cardImg="cardObj.card_images" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/general.scss";

.row {
  background-color: white;

  .col-2 {
    background-color: $mainColor;
  }
}
</style>
