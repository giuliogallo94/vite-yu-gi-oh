<script>
export default {
  props: {
    card: Object,
    cardImg: Object,
  },
};
</script>

<template>
  <div class="mb-4 text-center">
    <img v-for="img in card.card_images" :src="img.image_url_small" alt="" />
    <h3>{{ card.name }}</h3>
    <p>{{ card.archetype }}</p>
  </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
</style>
