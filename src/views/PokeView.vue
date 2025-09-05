<script setup>
import { useRoute, useRouter } from 'vue-router';
import { ref } from 'vue';
import axios from 'axios';

const route = useRoute();
const router = useRouter();
const name = route.params.name;
const pokemon = ref({});

const getData = async () => {
  try {
    const { data } = await axios.get(`https://pokeapi.co/api/v2/pokemon/${name}`);
    pokemon.value = data;
  } catch (error) {
    console.error('Error fetching Pokémon data:', error);
    pokemon.value = null;
    router.push('/not-found');
  }
};
getData();
</script>
<template>
  <div v-if="pokemon" class="container mt-5">
    <!-- 🤯 se puede sacar directamente el parámetro de la url -->
    <h1>Este es {{ $route.params.name }}</h1>
    <img
      :src="pokemon.sprites?.front_default"
      width="200"
      height="200"
      alt="Imagen de {{ pokemon.name }}"
    />
  </div>
</template>
