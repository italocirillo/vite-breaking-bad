<script>
export default {
    name: "AppHeader",
}
</script>

<template>
    <header>
        <img src="../assets/img/logo.svg" alt="logo">
        <h1>
            Yu-Gi-Oh Api
        </h1>
    </header>
</template>

<style lang="scss">
header {
    display: flex;
    padding: 1em;

    img {
        width: 10%;
        padding: 0em 1em;
    }

    h1 {
        font-weight: 900;
        padding: 0em 0.5em;
    }
}
</style>