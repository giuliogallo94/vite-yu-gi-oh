<script>
import CardsList from "./CardsList.vue";
import CardsStats from "./CardsStats.vue";

export default {
  components: {
    CardsList,
    CardsStats,
  },
};
</script>

<template>
  <div class="main px-5 pt-5">
    <div class="container p-5">
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
