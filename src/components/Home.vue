<script setup>

const name = "Login";
import UserLogin from './UserLogin.vue';

</script>

<template>
  <div>
    <div>
      <img class="logo" src="../assets/logo.png" alt="logo">
    </div>
    <h1 class="titleHome">{{ name }}</h1>
  </div>
</template>

<style scoped>
.logo {
  margin: auto;
  box-sizing: border-box;
  position:relative;
  align-items:center;
}
.titleHome {
  margin: 2rem;
  text-align: center;
}
</style>
