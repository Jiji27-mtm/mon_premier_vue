<script setup>
import { ref } from "vue";
 
const compteur = ref(0);

function augmenter() {
  compteur.value++;
}

function diminuer() {
  compteur.value--;
}
</script>

<template>
  <div>
    <h1>Compteur</h1>
    <h2>{{ compteur }}</h2>

    <button @click="augmenter">+</button>
    <button @click="diminuer">-</button>
  </div>
</template>
