<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import axios from "axios";
import { store } from "./store";

export default {
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then((resp) => {
      this.store.carte = resp.data.data;
      console.log(this.store.carte)
    })
  }
}
</script>

<template>
  <AppHeader title="Yu - Gi - Oh Api" />
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
