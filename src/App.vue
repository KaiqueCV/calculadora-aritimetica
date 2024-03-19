<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case '+':
          this.result = this.num1 + this.num2;
          break;
        case '-':
          this.result = this.num1 - this.num2;
          break;
        case '*':
          this.result = this.num1 * this.num2;
          break;
        case '/':
          if (this.num2 === 0) {
            this.result = 'Error: Division by zero';
          } else {
            this.result = this.num1 / this.num2;
          }
          break;
      }
    },
  },
};
</script>

<template>
  <div id="calculator">
    <input type="number" v-model.number="num1" @input="calculate" />
    <select v-model="operator" @change="calculate">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input type="number" v-model.number="num2" @input="calculate" />
    <p>Result: {{ result }}</p>
  </div>
</template>

<style scoped>
#calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 100px;
}

input,
select {
  margin: 5px;
}

p {
  color: green;
  font-weight: bold;
}
</style>