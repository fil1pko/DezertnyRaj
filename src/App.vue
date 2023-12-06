<script setup>
  import { ref } from 'vue';
  import navbar from './components/navbar.vue'
  import home from './components/home.vue'
  import markk from './components/mark.vue'
  import macronConfig from './components/configMacron.vue'

  const showHome = ref(true);
  const showMacron = ref(false);

  const handleHomeButtonClick = () => {
    showHome.value = false;
    showMacron.value = true;
  };

  const handleMacronButtonClick = () => {
    showHome.value = true;
    showMacron.value = false;
  };
</script>

<template>
  <header>
    <navbar />
  </header>

  <main>
    <home v-if="showHome" @buttonClick="handleHomeButtonClick" />
    <macronConfig v-if="showMacron" @buttonClick="handleMacronButtonClick"/>
    <markk />
  </main>

  <footer>
  </footer>
</template>

<style>
  @import './assets/style/main.scss';
  @import './assets/style/colors.scss';
</style>
