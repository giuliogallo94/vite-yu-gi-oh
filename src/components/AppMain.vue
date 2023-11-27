<script>
import CardsList from "./CardsList.vue";

export default {
  components: {
    CardsList,
  },
};
</script>

<template>
  <div class="main px-5 pt-5">
    <CardsList />
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.main {
  background-color: $mainColor;
  min-height: 90vh;
}
</style>
