<script setup>
const name = "Login";
import UserLogin from './UserLogin.vue';
</script>

<template>
  <div class="container">
    <div class="logo-container">
      <img class="logo" src="../assets/logo.png" alt="logo">
    </div>
    <h1 class="titleHome">{{ name }}</h1>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 50vh; /* Garante que o container ocupe a tela toda */
}

.logo-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.logo {
  max-width: 100%; /* Garante que o logo não ultrapasse os limites do container */
}

.titleHome {
  margin: 0;
  text-align: center;
}
</style>
