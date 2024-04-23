<script setup lang="ts">
import { RouterView } from 'vue-router';
import WebsiteHeader from '@/components/WebsiteHeader.vue';
import Footer from '@/components/WebsiteFooter.vue';
import DrawerMenu from '@/components/DrawerMenu.vue'
</script>

<template>
  <div class="drawer drawer-end">
    <input id="my-drawer" type="checkbox" class="drawer-toggle" />
    <div class="drawer-content">
      <!-- Page content here -->
      <WebsiteHeader />

      <Suspense>
        <main>
          <RouterView />
        </main>

        <template #fallback>
          <div>Loading...</div>
        </template>
      </Suspense>
      <Footer />
     </div> 
    <DrawerMenu />
  </div>
</template>

<style scoped>
</style>
