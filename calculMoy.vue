<script setup>
import { ref, computed } from "vue";

const ds = ref(0);
const tp = ref(0);
const ex = ref(0);

const moyenne = computed(() => {
  return (Number(ds.value) + Number(tp.value) + Number(ex.value)) / 3;
});

const mention = computed(() => {
  if (moyenne.value < 10) {
    return "Ajourné";
  } else if (moyenne.value < 12) {
    return "Passable";
  } else if (moyenne.value < 14) {
    return "Assez bien";
  } else if (moyenne.value < 16) {
    return "Bien";
  } else {
    return "Très bien";
  }
});
</script>

<template>
  <div>
    <h1>Calcul de moyenne</h1>
    <label>DS:</label>
    <input type="number" v-model="ds" />
    <br /><br />
    <label>TP:</label>
    <input type="number" v-model="tp" />
    <br /><br />
    <label>EX:</label>
    <input type="number" v-model="ex" />
    <br /><br />
    <h2>Moyenne:{{ moyenne.toFixed(2) }}</h2>
    <h2>Mention:{{ mention }}</h2>
  </div>
</template>
