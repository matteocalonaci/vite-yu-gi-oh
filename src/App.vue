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
      selected: "",
      cardUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=200&offset=0",
      archetypeUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php",
      allCards: [],
    }

  },

  methods: {

    getArchetype() {
      if (this.selected != "") {
        axios
          .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=" + this.selected)
          .then((result) => {
            this.store.cards = result.data.data;
          });
      }
    },
  },

  created() {

    // CHIAMATA X CARD
    axios
      .get(this.cardUrl)
      .then((risultato) => {
        this.store.cards = risultato.data.data;
        console.log(risultato.data.result)

      });


    // CHIAMATA X ARCHETIPI
    axios
      .get(this.archetypeUrl)
      .then((risultato) => {
        this.store.archetypeList = risultato.data;
        console.log(risultato.data)

      });

    this.getArchetpe;
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
        <select class="form-select" v-model="selected" @click="getArchetype">
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