<template>
  <div class="calculator">
    <h1>Arithmetic Calculator</h1>
    <div class="inputs">
      <!-- Number Inputs -->
      <input 
        v-model.number="num1" 
        type="number" 
        placeholder="Enter the first number"
      >
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">×</option>
        <option value="divide">÷</option>
      </select>
      <input 
        v-model.number="num2" 
        type="number" 
        placeholder="Enter the second number"
      >
    </div>
    <div class="result">
      <h2>Result: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: "add", // Default operation
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case "add":
          return this.num1 + this.num2;
        case "subtract":
          return this.num1 - this.num2;
        case "multiply":
          return this.num1 * this.num2;
        case "divide":
          return this.num2 !== 0 ? this.num1 / this.num2 : "Error: Division by zero";
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
.calculator {
  max-width: 400px;
  margin: 50px auto;
  text-align: center;
  font-family: Arial, sans-serif;
  background-color: aquamarine;
}

.inputs {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}

input,
select {
  width: 30%;
  padding: 10px;
  font-size: 16px;
}

.result h2 {
  margin-top: 20px;
  font-size: 24px;
  color: red;
}
</style>
