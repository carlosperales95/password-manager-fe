<template>
  <nav-bar></nav-bar>
  <router-view></router-view>
</template>

<script>
import { RouterView } from 'vue-router';
import NavBar from './components/layout/NavBar.vue';

export default {
  components: {
    RouterView,
    NavBar
  },
  setup() {
    
  },
}
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: 'Catamaran';font-size: 22px;
}

body {
  margin: 0;
  background-color: rgb(10, 14, 11);
  color: rgb(235, 235, 235);
}

section {
  margin: 2rem auto;
  margin-left: 2rem;
  margin-right: 2rem;
  border: 1px solid #ccc;
  border-radius: 12px;
  padding: 1rem;
}
</style>
