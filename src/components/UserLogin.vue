<template>
  <div class="container">
    <form class="formulario" @submit.prevent="autenticarAcesso">
      <label for="cnpj">CNPJ</label>
      <input
        type="text"
        v-model="dadosCnpj.cnpj"
        placeholder="Ex: 11.222.333/4444-55"
        @input="valideCnpj"
      />

      <label for="codigoEmpresa">Código Empresa</label>
      <input
        type="number"
        v-model="dadosCnpj.codEmpresa"
        placeholder="Ex: 123456"
        @input="valideCodEmpresa"
      />

      <div
        class="g-recaptcha"
        data-sitekey="6LdCxAcqAAAAADkQpk4P3QU5exJiVWk00vDNzLoQ"
      ></div>

      <button type="submit">Buscar</button>
    </form>

    <div class="footer">
      <h6>© Todos os direitos reservados 2024</h6>
      <h6>Aristóteles Aguiar</h6>
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const dadosCnpj = reactive({
  cnpj: "",
  codEmpresa: "",
});

const valideCnpj = () => {};

const valideCodEmpresa = () => {};

const autenticarAcesso = () => {
  const recaptchaResponse = grecaptcha.getResponse();
  if (recaptchaResponse.length === 0) {
    alert("Por favor, complete o reCAPTCHA.");
    return;
  }
  // Enviar recaptchaResponse para seu backend para validação
  console.log("reCAPTCHA response:", recaptchaResponse);
};

console.log(dadosCnpj.cnpj, dadosCnpj.codEmpresa);
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 30vh; 
  padding: 20px;
  background-color: #ffffff; 
}

.formulario {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  max-width: 400px; 
  background-color: #f9f9f9; 
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

label {
  margin: 0.5rem 0;
  font-weight: bold;
  color: #086EBA;
}

input {
  margin: 0.3rem 0 1rem 0;
  padding: 0.5rem;
  width: 100%;
  border: 1px solid #ccc;
  border-radius: 4px;
  text-align: center;
  box-sizing: border-box;
}

.g-recaptcha {
  margin: 2rem 0;
}

button {
  margin-top: 1rem;
  padding: 0.75rem 1.5rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 0.4rem;
  cursor: pointer;
  font-size: 1rem;
}

button:hover {
  background-color: #0056b3;
}

.footer {
  margin-top: 5px;
  text-align: center;
  color: #777;
}
</style>
