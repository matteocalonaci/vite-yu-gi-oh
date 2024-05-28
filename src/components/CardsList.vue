<!-- JS -->
<script>
import SingleCard from "./SingleCard.vue";
import store from '../data/store.js';
console.log(store)
export default {
    name: "CardsList",
    components: {
        SingleCard
    },
    data() {
        return {
            store
        }

    },
    mounted() {
        axios
            .get(
                "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
            )
            .then((risultato) => {
                this.store.cards = risultato.data.data;
            });
        console.log('mounted', this.store.cards)

    }


}
</script>


<!-- HTML -->
<template>
    <main>
        <!-- <div class="container">
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
        </div> -->
        <div class="container-fluid">
            <div class="row">
                <div class="col-1"></div>
                <div class="col-1 py-4">
                    <select class="form-select" aria-label="Default select example">
                        <option selected>Alien</option>
                        <option value="1">Infernoble Arms</option>
                        <option value="2">Melodious</option>
                        <option value="3">Noble Knight

                        </option>
                    </select>
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
    background-color: orange;
    padding: 1rem;
}

.min-height {
    min-height: 10rem;
}
</style>