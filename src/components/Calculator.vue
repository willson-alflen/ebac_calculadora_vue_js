<template>
  <div class="container mt-4">
    <h1 class="text-center mb-4">Calculadora Vue.js</h1>

    <div class="row">
      <div class="col-md-4">
        <input
          type="number"
          v-model="num1"
          class="form-control"
          @input="calculate"
        />
      </div>
      <div class="col-md-4">
        <select
          v-model="operator"
          class="form-select select-arrow-white"
          @change="calculate"
        >
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
      </div>
      <div class="col-md-4">
        <input
          type="number"
          v-model="num2"
          class="form-control"
          @input="calculate"
        />
      </div>
    </div>

    <div class="row mt-4">
      <div class="col-md-12">
        <h3 class="text-center">Result: {{ result }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: "+",
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case "+":
          this.result = this.num1 + this.num2;
          break;
        case "-":
          this.result = this.num1 - this.num2;
          break;
        case "*":
          this.result = this.num1 * this.num2;
          break;
        case "/":
          this.result = this.num1 / this.num2;
          break;
      }
    },
  },
};
</script>

<style scoped>
h1 {
  color: #41b883;
}

select {
  background-color: #35495e;
  color: white;
}

.select-arrow-white {
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 10 10"><path d="M5 7L1 3h8L5 7z" fill="%23fff"/></svg>');
  background-repeat: no-repeat;
  background-position: right 0.5rem center;
  background-size: 8px 8px;
  color: white;
}

input {
  border-color: #41b883;
}

.row {
  margin-bottom: 10px;
}

.text-center {
  text-align: center;
}

.mt-4 {
  margin-top: 1.5rem;
}

.mb-4 {
  margin-bottom: 1.5rem;
}

.mt-4 {
  margin-top: 1.5rem;
}
</style>
