<script setup>
/* import { RouterLink, RouterView } from 'vue-router' */
import Navbar from './components/Navbar/Navbar.vue';

</script>

<template>
  <Navbar />
  
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
  /* max-height: 100vh; */
}

.logo {
  margin-right: 1rem;
  padding: 20px;
  
}

nav {
  align-items: center;
  margin: 0 0 3rem 0;
  
  width: 100%;
  font-size: 15px;
}

.navbar {
  margin-bottom: 5rem;
  align-items: center;
  font-weight: bold;
  width: 120vw;
  background-color: hsla(160, 100%, 37%, 0.2);
  height: 120px;
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
    /* display: flex;
    place-items: center; */
    padding-right: calc(var(--section-gap) / 2);
  }

  /* header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  } */
/* 
  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  } */
}
</style>
