<script>
import { store } from "../store";
import CardsList from "./CardsList.vue";
import CardsStats from "./CardsStats.vue";
import AppLoader from "./AppLoader.vue";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    CardsList,
    CardsStats,
    AppLoader,
  },
};
</script>

<template>
  <div class="main px-5 pt-5">
    <AppLoader v-if="store.loading == true" />
    <div class="container p-5" v-else>
      <CardsStats />
      <CardsList />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/general.scss";

.main {
  background-color: $mainColor;
  min-height: 90vh;

  .container {
    background-color: white;
  }
}
</style>
