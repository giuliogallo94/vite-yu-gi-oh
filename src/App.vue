<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

import CardsList from "./components/CardsList.vue";
export default {
  data() {
    return {
      store,
    };
  },
  created() {
    // this.store.loading = true;
    axios.get(this.store.apiUrl).then((resp) => {
      this.store.cardsArray = resp.data.data;
      // this.store.loading = false;
    });
  },
  components: {
    AppHeader,
    AppMain,
  },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss" scoped>
@use "./style/general.scss";
</style>
