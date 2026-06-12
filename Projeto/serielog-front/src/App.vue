<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <nav class="top" id="top">
    <RouterLink to="/">Séries</RouterLink>
    |
    <RouterLink to="/series/nova">Nova Série</RouterLink>
  </nav>
  
  <RouterView />
</template>
