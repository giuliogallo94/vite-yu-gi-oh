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
  <div class="stats">
    <p class="p-3 m-0">Totale {{ store.cardsArray.length }} personaggi</p>
  </div>
</template>

<style lang="scss" scoped>
.stats {
  background-color: #21252a;
  color: white;
}
</style>
