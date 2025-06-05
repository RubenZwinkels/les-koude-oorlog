<template>
  <div class="cat-fact">
    <p v-if="loading">Een momentje, we halen een kattenfeit op...</p>
    <p v-else-if="error">{{ error }}</p>
    <p v-else>{{ fact?.fact }}</p>
    <button @click="fetchFact">Nieuwe cat fact</button>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
import CatFact from "@/models/catFact.ts";

const fact = ref<CatFact | null>(null);
const loading = ref(false);
const error = ref("");

const fetchFact = async () => {
  loading.value = true;
  error.value = "";
  try {
    const res = await fetch("https://catfact.ninja/fact");
    if (!res.ok) throw new Error("API-fout");
    const data = await res.json();
    fact.value = { fact: data.fact };
  } catch (err: any) {
    error.value = "Kon geen kattenfeit ophalen.";
  } finally {
    loading.value = false;
  }
};

onMounted(fetchFact);
</script>

<style scoped lang="scss">
@import "@/styles/variables.scss";

.cat-fact {
  padding: 1rem;
  background-color: white;
  border-radius: 0.5rem;
  font-family: sans-serif;

  button {
    margin-top: 1rem;
    padding: 0.5rem 1rem;
    background-color: $sov-red;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
}
</style>
