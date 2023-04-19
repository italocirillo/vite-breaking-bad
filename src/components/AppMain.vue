<script>
import MainCard from './MainCard.vue';
import { store } from '../store';

export default {
    name: "AppMain",
    data() {
        return {
            store,
        };
    },
    components: {
        MainCard
    }
}
</script>

<template>
    <main>
        <div class="container">
            <h2>Carte trovate: {{ store.carte.length }}</h2>
            <ul>
                <h2 class="loading" v-if="store.loading">Loading...</h2>
                <div class="row row-cols-5 g-4">
                    <div class="col" v-for="carta in store.carte" :key="carta.id">
                        <MainCard :carta="carta" />
                    </div>
                </div>
            </ul>
        </div>
    </main>
</template>

<style lang="scss">
@use "../styles/partials/variables" as*;

main {
    background-color: $background-color;
    padding: 3em;

    .container {
        padding: 2em;
        background-color: white;

        h2 {
            background-color: black;
            color: white;
            font-size: 0.8rem;
            padding: 1em;
        }

        .loading {
            background-color: cadetblue;
        }

        ul {
            padding: 0em;
        }
    }
}
</style>