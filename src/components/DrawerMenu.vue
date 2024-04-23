<script setup lang="ts">
import { RouterLink } from 'vue-router'
</script>

<template>
  <div class="drawer-side">
    <label for="my-drawer" aria-label="close sidebar" class="drawer-overlay"></label> 
    <ul class="menu p-4 w-80 min-h-full bg-base-200 text-base-content">
      <!-- Sidebar content here -->
      <li><RouterLink to="/">Home</RouterLink></li>
      <li><RouterLink to="/mitglieder">Mitglieder</RouterLink></li>
      <li><RouterLink to="/events">Events</RouterLink></li>
      <li><RouterLink to="/lieder">Stygli</RouterLink></li>
      <li><RouterLink to="/sujets">Sujets</RouterLink></li>
    </ul>
  </div>
</template>
<style scoped>
</style>