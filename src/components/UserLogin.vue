<script setup>
import { reactive } from "vue";
const dadosCnpj = reactive({
  cnpj: "",
  codEmpresa: "",
});

console.log(dadosCnpj.cnpj, dadosCnpj.codEmpresa);
</script>

<template>
  <div>
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
  </div>

  <p style="text-align: center">
     Teste de cnpj {{ dadosCnpj.cnpj }} codEmpresa {{ dadosCnpj.codEmpresa }}
  </p>
</template>

<style scoped>
.cnpj,
.codEmpresa {
  margin: 1rem;
  padding: 0.3rem;
  display: flex;
  text-align: center;
  align-items: center;
}
</style>
