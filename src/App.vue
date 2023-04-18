<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppSelector from './components/AppSelector.vue';
import axios from "axios";
import { store } from "./store";

export default {
  components: {
    AppHeader,
    AppMain,
    AppSelector
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    this.stampaCarte();
  },
  methods: {
    stampaCarte() {
      this.store.loading = true;
      const params = {};
      if (this.store.tipoSelezionato) {
        params.archetype = this.store.tipoSelezionato;
      }
      axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0", {
        params
      }).then((resp) => {
        this.store.carte = resp.data.data;
      }).catch(error => {
        console.log("errore:", error);
      }).finally(() => {
        this.store.loading = false;
      })
    },
    filtraCarte() {
      this.stampaCarte();
    }
  }
}
</script>

<template>
  <AppHeader title="Yu - Gi - Oh Api" />
  <AppSelector @filter="filtraCarte" />
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>
