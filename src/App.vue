<script setup>
import { reactive } from "vue";
import Formulario from "./components/Formulario.vue";
import Header from "./components/Header.vue";

const estado = reactive({
  filtro: "multiplicacao",
  numero1: 0,
  numero2: 0,
});

const multiplicacao = ({ numero1, numero2 } = estado) => {
  return numero1 * numero2;
};

const adicao = ({ numero1, numero2 } = estado) => {
  return numero1 + numero2;
};

const subtracao = ({ numero1, numero2 } = estado) => {
  return numero1 - numero2;
};

const divisao = ({ numero1, numero2 } = estado) => {
  return numero1 / numero2;
};

const matematica = () => {
  const { numero1, numero2, filtro } = estado;

  if ((numero1, numero2)) {
    switch (filtro) {
      case "multiplicacao":
        return multiplicacao();
      case "adicao":
        return adicao();
      case "subtracao":
        return subtracao();
      case "divisao":
        return divisao();
    }
  }
};
</script>

<template>
  <div class="container">
    <Header />
    <Formulario
      :trocar-filtro="(event) => (estado.filtro = event.target.value)"
      :valor-numero1="(event) => (estado.numero1 = Number(event.target.value))"
      :valor-numero2="(event) => (estado.numero2 = Number(event.target.value))"
    />

    <p class="mt-4 fs-2 text-center">O resultado é {{ matematica() }}</p>
  </div>
</template>

<style scoped>
</style>
