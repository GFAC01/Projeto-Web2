<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <nav>
    <RouterLink to="/">Séries</RouterLink>
    |
    <RouterLink to="/series/nova">Nova Série</RouterLink>
  </nav>
  
  <RouterView />
</template>