<script setup>
import { reactive } from "vue";
const dadosCnpj = reactive({
  cnpj: "",
  codEmpresa: "",
});

console.log(dadosCnpj.cnpj, dadosCnpj.codEmpresa);
</script>

<template>
  <div class="container">
    <form class="formulario">
      <label for="cnpj">CNPJ</label><br />
      <input
        type="text"
        v-model="dadosCnpj.cnpj"
        placeholder="Ex: 11.222.333/4444-55"
        @input="valideCnpj"
      /><br />

      <label for="codigoEmpresa">Código Empresa</label><br />
      <input
        type="number"
        v-model="dadosCnpj.codEmpresa"
        placeholder="Ex: 123456"
        @input="valideCodEmpresa"
      /><br />
    </form>
    <p>
      Teste de cnpj {{ dadosCnpj.cnpj }} codEmpresa {{ dadosCnpj.codEmpresa }}
    </p>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 40vh; /* Garante que o container ocupe a tela toda */
  text-align: center; /* Centraliza o texto */
}

.formulario {
  display: flex;
  flex-direction: column;
  align-items: center;
}

label {
  margin: 0.2rem 0;
}

input {
  margin: 0.2rem 0 0 0;
  padding: 0.3rem 0;
  text-align: center;
}

p {
  margin-top: 0.2rem;
}
</style>
