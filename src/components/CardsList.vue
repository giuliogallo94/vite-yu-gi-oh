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
  <div class="row row-cols-5">
    <div class="col mb-4" v-for="cardObj in store.cardsArray">
      <AppCard :card="cardObj" :cardImg="cardObj.card_images" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.row {
  background-color: white;
}
</style>
