<script>
export default {};
</script>

<template>
  <header class="py-3 d-flex align-items-center">
    <div class="logo text-center">
      <img src="../assets/img/logo.png" alt="" />
    </div>
    <div class="title">
      <h1>Yu-Gi-Oh Api</h1>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use "../style/general.scss";
// @use "../style/partials/variables" as *;

header {
  background-color: white;
  width: 100vw;

  .logo {
    width: 150px;

    img {
      max-width: 60%;
    }
  }
}
</style>
