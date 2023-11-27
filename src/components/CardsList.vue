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
  <div class="container p-4">
    <div class="row">
      <div class="col" v-for="cardObj in store.cardsArray">
        <AppCard :card="cardObj" :cardImg="cardObj.card_images" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.container {
  background-color: blue;
  padding: 2rem;

  .row {
    background-color: white;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: stretch;
    text-align: center;
    gap: 1rem;

    .col {
      width: calc(100% / 5 - 1rem);
      background-color: $mainColor;
    }
  }
}
</style>
