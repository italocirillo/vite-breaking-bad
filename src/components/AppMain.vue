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
    components: { MainCard }
}
</script>

<template>
    <main>
        <div class="container">
            <h2>Carte trovate: 20</h2>
            <ul>
                <div class="row row-cols-4">
                    <div class="col">
                        <MainCard />
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

        ul {
            padding: 0em;
        }
    }
}
</style>