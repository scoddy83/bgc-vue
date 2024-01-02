<script setup lang="ts">
  import Mitglied from '../components/MitgliedPreview.vue'
  import client from '../services/client'

  const query = `*[_type == "mitglied"] {
  vorname,
  name,
  }[0...10]`;

  const mitglieder = await client.fetch(query);
  
</script>

<template>
  <div class="mitglieder">
    <h1>Mitglieder</h1>
    <Mitglied />
    <p>Die Mitglieder der BGC</p>
    <div>
      <ul>
        <li v-for="mitglied in mitglieder" :key="mitglied._id">
          {{ mitglied.vorname }} {{ mitglied.name }}
        </li>
      </ul>
    </div>
  </div>
</template>

<style>
</style>
../services/Client../services/client