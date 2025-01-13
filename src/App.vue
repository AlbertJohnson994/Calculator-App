<template>
  <div class="app">
    <div class="calculator">
      <h1>Arithmetic Calculator</h1>
      <div class="inputs">
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
    <footer class="social-footer">
      <div class="social-footer__content">
        <p class="social-footer__text">Follow me on:</p>
        <ul class="social-footer__icons">
          <li>
            <a href="https://www.facebook.com" target="_blank" title="Facebook">
              <i class="fab fa-facebook-f"></i>
            </a>
          </li>
          <li>
            <a href="https://www.instagram.com" target="_blank" title="Instagram">
              <i class="fab fa-instagram"></i>
            </a>
          </li>
          <li>
            <a href="https://www.twitter.com" target="_blank" title="Twitter">
              <i class="fab fa-twitter"></i>
            </a>
          </li>
          <li>
            <a href="https://www.tiktok.com" target="_blank" title="TikTok">
              <i class="fab fa-tiktok"></i>
            </a>
          </li>
          <li>
            <a href="https://www.youtube.com" target="_blank" title="YouTube">
              <i class="fab fa-youtube"></i>
            </a>
          </li>
        </ul>
      </div>
      <p class="footer__text text">
        &copy; 2025 - Developed by Albert Johnson. This project is available at 
        <a href="https://github.com/AlbertJohnson994" target="_blank" rel="noopener noreferrer">
          GitHub
        </a>.
      </p>
    </footer>
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
.app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.calculator {
  max-width: 400px;
  margin: 50px auto;
  text-align: center;
  font-family: Arial, sans-serif;
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
  font-size: 42px;
  color: red;
}

/* Footer Styles */
.social-footer {
  text-align: center;
  margin-top: 50px;
  padding: 20px;
  background-color: #f4f4f4;
}

.social-footer__text {
  margin-bottom: 10px;
  font-weight: bold;
}

.social-footer__icons {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: center;
  gap: 15px;
}

.social-footer__icons li {
  display: inline-block;
}

.social-footer__icons a {
  text-decoration: none;
  font-size: 20px;
  color: #333;
  transition: color 0.3s ease;
}

.social-footer__icons a:hover {
  color: #007bff;
}

.footer__text {
  margin-top: 10px;
  font-size: 14px;
}
</style>
