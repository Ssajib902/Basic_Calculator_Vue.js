<template>
    <div id="settings">
      <header>
        <nav>
          <ul>
            <li><router-link to="/">Calculator</router-link></li>
            <li><router-link to="/history">History</router-link></li>
            <li><router-link to="/settings">Settings</router-link></li>
          </ul>
        </nav>
      </header>
      <h2>Settings</h2>
      <div class="option">
        <label>Font Size:</label>
        <button @click="changeFontSize(-1)">-</button>
        <button @click="changeFontSize(1)">+</button>
      </div>
      <div class="option">
        <label>Theme Color:</label>
        <button v-for="color in colors" :key="color" :style="{ background: color }" @click="changeTheme(color)"></button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        colors: ['#f00', '#0f0', '#00f', '#ff0', '#0ff', '#808080', '#008000', '#f8f8ff', '#00ffff'],

      };
    },
    methods: {
      changeFontSize(amount) {
        document.body.style.fontSize = `${parseInt(getComputedStyle(document.body).fontSize) + amount}px`;
      },
      changeTheme(color) {
        document.body.style.backgroundColor = color;
      },
    },
  };
  </script>
  
  <style scoped>
  #settings {
    padding: 20px;
    max-width:400px;
    height: 400px;
    margin: 50px auto;
    border: 2px solid #ccc;
    border-radius: 10px;
    background: #fff;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  }
  header {
    width: 100%;
    background: #4CAF50;
    color: #fff;
    padding: 10px 0;
    text-align: center;
    border-bottom: 2px solid #ccc;
    border-radius: 10px;
  }
  nav ul {
    display: flex;
    justify-content: center;
    list-style: none;
    padding: 0;
    margin: 0;
  }
  nav ul li {
    margin: 0 10px;
  }
  nav ul li a {
    color: #fff;
    text-decoration: none;
    font-weight: bold;
  }
  nav ul li a:hover {
    text-decoration: underline;
  }
  h2 {
    text-align: center;
    color: #333;
  }
  .option {
    margin: 20px 0;
  }
  label {
    display: block;
    margin-bottom: 10px;
    font-weight: bold;
    color: #555;
  }
  button {
    margin-right: 10px;
    padding: 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s;
  }
  button:hover {
    opacity: 0.8;
  }
  </style>
  