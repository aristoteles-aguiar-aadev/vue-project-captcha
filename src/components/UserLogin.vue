<template>
  <div class="container">
    <form class="formulario" @submit.prevent="autenticarAcesso">
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

      <div
        class="g-recaptcha"
        data-sitekey="6LdCxAcqAAAAADkQpk4P3QU5exJiVWk00vDNzLoQ"
      ></div>

      <button type="submit">Autenticar Acesso</button>
    </form>

    <div class="footer">
      <h6>© Todos os direitos reservados 2024</h6>
      <h6>Aristóteles Aguiar</h6><br>
     
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
  height: 40vh;
  text-align: center;
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

.g-recaptcha {
  margin: 1rem 0;
}

button {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 0.25rem;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

p {
  margin-top: 0.2rem;
}
.footer {
  margin: 2rem;
}
</style>
