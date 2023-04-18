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
    <select class="form-select" name="tipo" id="tipo" v-model="store.tipoSelezionato" @change="$emit('filter')">
        <option value="">Tutti</option>
        <option :value="tipo" v-for="tipo in tipi">{{ tipo }}</option>
    </select>
</template>

