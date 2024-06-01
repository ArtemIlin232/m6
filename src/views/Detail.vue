<script setup>
import {DetailGame} from "../api.js";
import {useRoute} from "vue-router";
import {onBeforeMount, ref} from "vue";

let detail = ref()
let route = useRoute()

onBeforeMount(async () => {
    detail.value = await DetailGame(route.params.id);
});

</script>


<template>
    <section> 
        <nav>
            <img v-for="(scren, index) in detail.screenshots" :key="index" :src="scren.image" />
         </nav>
             <h1>{{detail.title}} </h1>
             <p>{{detail.description}} </p>
    </section>
</template>

<style scoped> 
 section {
    padding: 20px;
 }
 nav {

    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
    grid-gap: 50px
 }
 img {
    width: 40%;
    aspect-ratio: 16/9;
 }
 h1 {
    font-size: 50px;
    text-align: center;
    margin-top: 20px;
    color: aliceblue;
 }
 p{ 
    font-size: 24px;
    margin-top: 20px;
    color: aliceblue;
    text-align: center;
    line-height: 1.2;
 }
</style>