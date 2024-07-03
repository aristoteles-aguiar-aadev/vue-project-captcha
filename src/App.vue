<script setup>
import Home from "./components/Home.vue";
import UserLoginVue from "./components/UserLogin.vue";
</script>

<template>
  <header>
    <home />
  </header>

  <main>
    <UserLoginVue />
  </main>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
}
</style>
