<template>
  <div class="calculator">
    <h2>Calculadora Aritmética</h2>
    <div>
      <label for="number1">Número 1:</label>
      <input type="number" v-model.number="number1" />
    </div>
    <div>
      <label for="number2">Número 2:</label>
      <input type="number" v-model.number="number2" />
    </div>
    <div>
      <label for="operation">Operação:</label>
      <select v-model="operation">
        <option value="+">Adição (+)</option>
        <option value="-">Subtração (-)</option>
        <option value="*">Multiplicação (*)</option>
        <option value="/">Divisão (/)</option>
      </select>
    </div>
    <div>
      <h3>Resultado: {{ result }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: '+',
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case '+':
          return this.number1 + this.number2;
        case '-':
          return this.number1 - this.number2;
        case '*':
          return this.number1 * this.number2;
        case '/':
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
*{
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  justify-content: center;
  text-decoration: none;
  background-color: transparent;
}
.calculator {
  max-width: 300px;
  margin: 0 auto;
  text-align: center;
  
}
input,
select {
  margin: 15px 0;
  padding: 10px;
  text-align: center;
  
}
h2{
  color: red;
  padding:15px;
  box-shadow: inset;
}
h3{
  text-align: center;
}
.operation{
  padding: 10px;
}
label{
 padding: 10px 0;
 margin: 15px 0;
 
}
</style>
