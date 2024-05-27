<!-- JS -->
<script>
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';
export default {
  name: "App",
  components: {
    AppHeader,
    CardsList,
  },

  data() {
    return {

    }

  }

}
</script>


<!-- HTML -->
<template>
  <AppHeader />
  <CardsList />

</template>


<!-- CSS -->
<style scoped></style>