<script>
import AppHeader from "./components/AppHeader.vue";
export default {
  data() {
    return {
      // store,
    };
  },
  created() {
    // this.store.loading = true;
    // axios.get(this.store.apiUrl).then((resp) => {
    //   this.store.characters = resp.data.results;
    //   this.store.loading = false;
    // });
  },
  components: { AppHeader },
};
</script>

<template><AppHeader /></template>

<style lang="scss" scoped>
@use "./style/general.scss";
</style>
