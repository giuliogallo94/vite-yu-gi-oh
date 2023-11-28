<script>
export default {};
</script>

<template>
  <div class="change-page d-flex flex-column align-items-center w-25 mx-auto">
    <span>Change Page</span>
    <div class="buttons d-flex my-2">
      <div class="prev me-3">
        <button @click="$emit(`prevPage`)">&leftarrow;</button>
      </div>
      <div @click="$emit(`nextPage`)" class="next">
        <button>&rightarrow;</button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
