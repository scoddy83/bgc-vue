<script setup lang="ts">
</script>

<template>
  <header>
    <div class="navbar bg-base-100">
      <div class="flex-1">
        <img alt="Basler Garde-Clique Logo" class="logo" src="@/assets/logo.svg" width="50" height="50" />
        <a class="btn btn-ghost text-xl">Basler Garde Clique</a>
      </div>
      <div class="flex-none">
        <label for="my-drawer" class="btn btn-square btn-ghost">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="inline-block w-5 h-5 stroke-current"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z"></path></svg>
        </label>
      </div>
    </div>
  </header>
  
</template>

<style scoped>
@font-face {
  font-family: LithosProBlack;
  src: url(../assets/fonts/LithosPro-Black.otf);
  font-weight: bold;
}

header {
  line-height: 1.5;
  max-height: 100px;
  width: 100%;
  background-color: rgb(0, 0, 88, 0.2);
  font-family: LithosProBlack;
  position: fixed;
}

.logo {
  display: none;
}

nav {
  width: 100%;
  font-size: 32px;
  text-align: right;
  /*margin-top: 2rem;*/
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: #000099;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

/*
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
*/
</style>