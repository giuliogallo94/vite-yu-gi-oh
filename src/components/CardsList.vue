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
  <div class="container">
    <div class="row p-2">
      <div class="col" v-for="cardObj in store.cardsArray">
        <AppCard :card="cardObj" :cardImg="cardObj.card_images" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.container {
  background-color: white;
}
</style>
