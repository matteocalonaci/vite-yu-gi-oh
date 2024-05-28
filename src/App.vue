<!-- JS -->
<script>
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';
import store from './data/store.js';
import axios from "axios";

export default {
  name: "App",
  components: {
    AppHeader,
    CardsList,
    store

  },

  data() {
    return {
      store,
      selected: ""
    }

  },
  created() {

    // CHIAMATA X CARD
    axios
      .get(
        "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=15"
      )
      .then((risultato) => {
        this.store.cards = risultato.data.data;
        console.log(risultato.data.result)

      });


    // CHIAMATA X ARCHETIPI
    axios
      .get(
        "https://db.ygoprodeck.com/api/v7/archetypes.php")
      .then((risultato) => {
        this.store.archetypeList = risultato.data;
        console.log(risultato.data)

      });
  },


}
</script>


<!-- HTML -->
<template>
  <AppHeader />
  <div class="container-fluid">
    <div class="row">
      <div class="col-1"></div>
      <div class="col-1 p-4">
        <select class="form-select" v-model="selected">
          <option selected value="">Seleziona Archetipo</option>
          <option v-for="archetype in store.archetypeList">{{ archetype.archetype_name }}</option>
        </select>
      </div>
    </div>
  </div>
  <CardsList />

</template>


<!-- CSS -->
<style scoped>
.row {
  background-color: orange;
}

.form-select {
  width: 15rem;
}
</style>