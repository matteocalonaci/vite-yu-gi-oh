<script>
export default {
    name: "SingleCard",
    props: ["dati"],
    data() {
        return {

        }
    }
}
</script>
<template>
    <div class="card col-2 myBg">
        <div class="img bg-warning">
            <img :src="dati.card_images[0].image_url" alt="Card image">
        </div>
        <h5 class=" text-center text-white p-2">{{ dati.name }}</h5>
        <p class=" text-center text-white p-2">{{ dati.archetype }}</p>

    </div>
</template>

<!-- CSS -->
<style scoped>
.col-2 {
    width: calc(100% / 3.5 - 8rem);
    margin-bottom: 1rem;
    padding: 0.0001rem 0;
}

.col-2 img {
    height: 100%;
    width: 100%;

}

.myBg {
    background-color: rgb(212, 143, 56);
}
</style>