<script>
export default {
    name: "MainCard",
    props: {
        carta: Object,
    }
}
</script>

<template>
    <div class="card">
        <img :src="carta.card_images[0].image_url" class="card-img-top" alt="">
        <div class="card-body">
            <h5 class="card-title">{{ carta.name }}</h5>
            <p class="card-text">{{ carta.archetype }}</p>
        </div>
    </div>
</template>

<style lang="scss">
@use "../styles/partials/variables" as*;

.card {
    text-align: center;

    .card-body {
        background-color: $background-color;
        padding-bottom: 2em;

        h5 {
            font-size: 1rem;
            text-transform: uppercase;
            font-weight: bolder;
            color: white;
        }

        p {
            font-size: 1.2rem;
        }
    }

}
</style>