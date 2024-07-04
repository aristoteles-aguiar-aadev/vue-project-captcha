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
  position: relative;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 70vh;
  background-color: #f5f5f5; /* Adiciona um fundo leve */
  padding: 20px;
  border-bottom: 1px solid #ddd; /* Adiciona uma linha inferior para separação */
}

.logo-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px; /* Espaço entre o logo e o título */
}

.logo {
  max-width: 80%; /* Garante que o logo não ultrapasse os limites do container */
  height: auto;
}

.titleHome {
  margin: 1rem;
  text-align: center;
  font-size: 2rem; /* Ajuste o tamanho da fonte */
  color: #333; /* Cor do texto */
}
</style>
