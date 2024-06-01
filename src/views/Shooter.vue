<script setup>
import Card from "../components/Card.vue";
import { GamesCategory } from "../api.js";
import { onBeforeMount, ref } from "vue";
let games = ref();
onBeforeMount(async () => {
    games.value = await GamesCategory("shooter");
});
</script>

<template>
    <section>
        <Card v-for="i in games" :key="i" :game="i" />
    </section>
</template>

<style scoped>
section {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    grid-gap: 20px;
    padding: 20px;
}
</style>