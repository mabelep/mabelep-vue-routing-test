<script setup>
import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
  <nav class="navbar bg-body-tertiary">
    <div class="container">
      <router-link
        to="/"
        class="navbar-brand d-flex align-items-center"
        href="#"
        style="height: 100%"
      >
        <img
          src="@/assets/pokemon-logo.svg"
          alt="Logo"
          width="50%"
          class="d-inline-block align-text-top me-2"
        />
        Pokemon API Test 🚀🚀🚀
      </router-link>
      <div>
        <RouterLink class="btn btn-outline-primary me-2" to="/">Home</RouterLink>
        <RouterLink class="btn btn-outline-primary" to="/pokemons">Pokemons</RouterLink>
      </div>
    </div>
  </nav>
  <div class="container">
    <RouterView />
  </div>
</template>
