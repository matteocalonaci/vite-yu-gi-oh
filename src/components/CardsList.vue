<!-- JS -->
<script>
import SingleCard from "./SingleCard.vue";
import store from '../data/store.js';

export default {
    name: "CardsList",
    components: {
        SingleCard
    },
    data() {
        return {
            store
        }

    }

}
</script>


<!-- HTML -->
<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="input-group mb-3">
                    <button class="btn btn-outline-secondary dropdown-toggle p-2 bg-white" type="button"
                        data-bs-toggle="dropdown" aria-expanded="false">Alien </button>
                    <ul class="dropdown-menu">
                        <li><a class="dropdown-item" href="#">Action</a></li>
                        <li><a class="dropdown-item" href="#">Another action</a></li>
                        <li><a class="dropdown-item" href="#">Something else here</a></li>
                        <li>
                            <hr class="dropdown-divider">
                        </li>
                        <li><a class="dropdown-item" href="#">Separated link</a></li>
                    </ul>
                </div>


            </div>
        </div>
        <div class="container bg-white p-5">

            <div class="container">
                <div class="row bg-black">
                    <span class="text-white p-3">Found 39 cards</span>
                </div>
                <div class="row d-flex justify-content-between min-height ">
                    <SingleCard v-for="card in store.cards" :card="card" />


                </div>
            </div>
        </div>
    </main>
</template>


<!-- CSS -->
<style scoped>
main {
    background-color: rgb(212, 143, 56);
    padding: 1rem;
}

.min-height {
    min-height: 10rem;
}
</style>