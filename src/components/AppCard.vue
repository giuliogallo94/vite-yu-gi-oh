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
    <div class="card-info p-2">
      <h5>{{ card.name }}</h5>
      <p>{{ card.archetype }}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/general.scss";

.my-card {
  img {
    width: 100%;
  }

  h5 {
    color: white;
  }
}
</style>
