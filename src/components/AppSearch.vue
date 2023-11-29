<script>
import { store } from "../store";
export default {
  data() {
    return {
      store,
      archetypes: ["Alien", "Ally of Justice", "Ancient Gear"],
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
      @change="$emit(`cardChoice`)">
      <option value=""></option>
      <option
        v-for="(archetype, index) in archetypes"
        :key="index"
        :value="archetype">
        {{ archetype }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/general.scss";
</style>
