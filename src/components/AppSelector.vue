<script>
import { store } from '../store';

export default {
    name: "AppSelector",
    emits: ["filter"],
    data() {
        return {
            store,
            tipi: ["Alien", "Ally of Justice", "Ancient Gear"]
        }
    }
}
</script>

<template>
    <div class="sezione-selettore">
        <div class="container">
            <select class="form-select" name="tipo" id="tipo" v-model="store.tipoSelezionato" @change="$emit('filter')">
                <option value="">Tutti</option>
                <option :value="tipo" v-for="tipo in tipi">{{ tipo }}</option>
            </select>
        </div>
    </div>
</template>

<style lang="scss">
@use "../styles/partials/variables" as*;

.sezione-selettore {
    background-color: $background-color;
    padding: 2em 2em 0em 0em;

    .form-select {
        width: 40%;
    }
}
</style>

