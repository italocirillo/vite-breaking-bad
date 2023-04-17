<script>
export default {
    name: "MainCard",
}
</script>

<template>
    <div class="card" style="width: 18rem;">
        <img src="https://images.ygoprodeck.com/images/cards_cropped/34541863.jpg" class="card-img-top" alt="">
        <div class="card-body">
            <h5 class="card-title">Card title</h5>
            <p class="card-text">Alien</p>
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
            font-size: 2rem;
            text-transform: uppercase;
            font-weight: 900;
            color: white;
        }

        p {
            font-size: 1.2rem;
        }
    }

}
</style>