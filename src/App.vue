<template>
  <div>
    <h1>Calculadora Aritmética</h1>
      <input type="number" v-model="firstValue" placeholder="Primeiro valor" />
      <input type="number" v-model="secondValue" placeholder="Segundo valor" />

    <select v-model="selectedOperation">
      <option value="#">Selecione a operação</option>
      <option value="soma">Adição</option>
      <option value="subtracao">Subtração</option>
      <option value="divisao">Divisão</option>
      <option value="multiplicacao">Multiplicação</option>
    </select>

    <p>Resultado: {{ calculateResult }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstValue: 0,
      secondValue: 0,
      selectedOperation: "#"
    };
  },
  computed: {
    calculateResult() {
      if (this.selectedOperation === "soma") {
        return this.firstValue + this.secondValue;
      } else if (this.selectedOperation === "subtracao") {
        return this.firstValue - this.secondValue;
      } else if (this.selectedOperation === "divisao") {
        return this.firstValue / this.secondValue;
      } else if (this.selectedOperation === "multiplicacao") {
        return this.firstValue * this.secondValue;
      } else {
        return "Selecione uma operação válida";
      }
    }
  }
};
</script>