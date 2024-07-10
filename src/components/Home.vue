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
  height: 50vh;
  background-color: #ffffff;
  padding: 20px;
  border-bottom: 1px solid #ddd;
}

.logo-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 2px;
}

.logo {
  max-width: 100dvw; 
  height: 40dvh;
}

.titleHome {
  margin: 0;
  text-align: center;
  font-size: 1.9rem; 
  color: #086EBA; 
}
</style>
