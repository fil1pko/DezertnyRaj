<script setup>
  import { ref } from 'vue';
  import navbar from './components/navbar.vue'
  import home from './components/home.vue'
  import markk from './components/mark.vue'
  import macronConfig from './components/configMacron.vue'
  import cakeConfig from './components/configCake.vue'

  const showHome = ref(true);
  const showMacron = ref(false);
  const showCake = ref(false);

  // choose between cake and macron
  const handleHomeButtonClick = () => {
    showHome.value = false;
    showMacron.value = true;
  };
  const handleHomeButtonClick2 = () => {
    showHome.value = false;
    showCake.value = true;
  };

  // back to home buttons
  const handleMacronButtonClick = () => {
    showHome.value = true;
    showMacron.value = false;
  };
  const handleCakeButtonClick = () => {
    showHome.value = true;
    showCake.value = false;
  };

</script>

<template>
  <header>
    <navbar />
  </header>

  <main>
    <home v-if="showHome" @buttonClick="handleHomeButtonClick" @buttonClick2="handleHomeButtonClick2" />
    <macronConfig v-if="showMacron" @buttonClick="handleMacronButtonClick"/>
    <cakeConfig v-if="showCake" @buttonClick="handleCakeButtonClick" />
    <markk />
  </main>

  <footer>
  </footer>
</template>

<style>
  @import './assets/style/main.scss';
  @import './assets/style/colors.scss';
</style>
