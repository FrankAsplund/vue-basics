<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
      <nav>
        <div class="navbar">
          <img
      alt="logo"
      class="logo"
      src="@/assets/logga.png"
      width="120"
      height="120"
    />
    <h1>Vue project</h1>
    <div class="router">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
      <RouterLink to="/test1">Test1</RouterLink>
      <RouterLink to="/test2">Test2</RouterLink>
    </div>
        </div>
      </nav>
  </header>

  <RouterView />
</template>

<style scoped>


h1 {
  margin-right: 1rem;
}

.router {
  margin-left: 3rem;
}


header {
  width: 2rem;
  position: absolute;
  top: 0px;
  line-height: 1.5;
}

.logo {
  margin-right: 1rem;
  padding: 20px;
  
}

nav {
  align-items: center;
  margin: 0 0 3rem 0;
  
  width: 100vw;
  font-size: 15px;
}

.navbar {
  margin-bottom: 5rem;
  align-items: center;
  font-weight: bold;
  width: 100%;
  background-color: hsla(160, 100%, 37%, 0.2);
  height: 100px;
  display: flex;
  padding: 30px;
  border-radius: 0px 0px 7px 7px;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    padding-right: calc(var(--section-gap) / 2);
  }
}
</style>