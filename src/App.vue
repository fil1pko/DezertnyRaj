<script setup>
  import navbar from './components/navbar.vue'
  import home from './components/home.vue'
  import markk from './components/mark.vue'
</script>

<template>
  <header>
    <navbar />
  </header>

  <main>
    <home />
    <markk />
  </main>

  <footer>
  </footer>
</template>

<style>
  @import './assets/style/main.scss';
  @import './assets/style/colors.scss';
</style>
