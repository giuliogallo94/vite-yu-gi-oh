<script>
import { store } from "../store";
export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="stats mx-2">
    <p class="p-3 m-0">Totale {{ store.cardsArray.length }} personaggi</p>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/general.scss";
.stats {
  background-color: #21252a;
  color: white;
}
</style>
