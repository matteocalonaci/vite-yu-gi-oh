<!-- JS -->
<script>
import store from '../data/store.js';

export default {
    name: "AppHeader",
    data() {
        return {

        }

    }

}
</script>


<!-- HTML -->
<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="col-1  p-2">
                    <img src="../assets/Yugioh_anime_logo.webp" alt="logo">
                </div>
                <div class="col-1"></div>
                <div class="col-10 text-end p-2">
                    <h1>Yu-Gi-Oh Api</h1>
                </div>
            </div>
        </div>
    </header>

</template>


<!-- CSS -->
<style scoped>
img {
    width: 10rem;
}
</style>