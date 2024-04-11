<script setup>
import { reactive } from "vue";

const estado = reactive({
  num1: 0,
  num2: 0,
  operacao: 'soma'
});

function calcular() {
  const num1 = parseFloat(estado.num1);
  const num2 = parseFloat(estado.num2);

  switch (estado.operacao) {
    case 'soma':
      return num1 + num2;
    case 'subtracao':
      return num1 - num2;
    case 'multiplicacao':
      return num1 * num2;
    case 'divisao':
      return num1 / num2;
    default:
      return 0;
  }
}
</script>

<template>
  <div class="main">
    <h1>Calculadora</h1>
    <input type="number" v-model="estado.num1" placeholder="Número 1">
    <input type="number" v-model="estado.num2" placeholder="Número 2">
    <select v-model="estado.operacao">
      <option value="soma">Soma</option>
      <option value="subtracao">Subtração</option>
      <option value="divisao">Divisão</option>
      <option value="multiplicacao">Multiplicação</option>
    </select>
    <h2>Resultado: {{ calcular() }}</h2>
  </div>
</template>

<style scoped>
* {
  font-family: Helvetica;
}

.main{
  background-color: rgb(223, 173, 82);
  width: 30%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
  border-radius: 8px
}

input, select{
  border: none;
  padding: 6px;
  border-radius: 4px;
}

</style>
