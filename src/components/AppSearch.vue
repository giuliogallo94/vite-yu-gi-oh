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
  <div>
    <span>Search by Archetype:</span>
    <select
      class="form-select form-select-sm mb-4 w-25"
      aria-label="Small select example"
      v-model="store.archetypeChoice"
      @change="$emit(`cardChoise`)">
      <option value="Alien">Alien</option>
      <option value="Ally of Justice">Ally of Justice</option>
      <option value="Ancient Gear">Ancient Gear</option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/general.scss";
</style>
