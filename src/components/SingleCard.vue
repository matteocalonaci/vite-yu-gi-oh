<script>
export default {
    name: "SingleCard",
    props: {
        card: Object
    },
    data() {
        return {

        }
    }
}
</script>
<template>
    <div class="card col-2 myBg">
        <div class="img bg-warning">
            <img :src="card.card_images[0].image_url" alt="">
        </div>
        <h5 class=" text-center text-white p-2">{{ card.name }}</h5>
        <p class=" text-center text-white p-2">{{ card.archetype }}</p>

    </div>
</template>

<!-- CSS -->
<style scoped>
.col-2 {
    width: calc((100% - 5rem) / 5);
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