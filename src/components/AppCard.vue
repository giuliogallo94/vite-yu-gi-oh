<script>
export default {
  props: {
    card: Object,
    cardImg: Object,
  },
};
</script>

<template>
  <div class="mb-4 text-center my-card">
    <img v-for="img in card.card_images" :src="img.image_url_small" alt="" />

    <h5 class="my-4">{{ card.name }}</h5>
    <p>{{ card.archetype ? card.archetype : "No Archetype" }}</p>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;

.my-card {
  height: 100%;
  background-color: $mainColor;

  img {
    width: 100%;
  }

  h5 {
    color: white;
  }
}
</style>
