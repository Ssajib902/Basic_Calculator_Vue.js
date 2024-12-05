<template>
    <div id="history">
      <header>
        <nav>
          <ul>
            <li><router-link to="/">Calculator</router-link></li>
            <li><router-link to="/history">History</router-link></li>
            <li><router-link to="/settings">Settings</router-link></li>
          </ul>
        </nav>
      </header>
      <h2>Calculation History</h2>
      <ul>
        <li v-for="(item, index) in history" :key="index">{{ item }}</li>
      </ul>
      <button @click="clearHistory">Reset History</button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        history: [
          '5 + 5 = 10',
          '6 * 6 = 36',
          '10 / 2 = 5'
        ],
      };
    },
    methods: {
      clearHistory() {
        this.history = [];
      },
    },
  };
  </script>
  
  <style scoped>
  #history {
    padding: 20px;
    max-width: 400px;
    height: 400px;
    margin: 50px auto;
    border: 2px solid #ccc;
    border-radius: 10px;
    background: #fff;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  }
  header {
    width: 100%;
    height: 30px;
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
  ul {
    list-style: none;
    padding: 0;
  }
  li {
    margin: 5px 0;
    padding: 5px;
    border-bottom: 1px solid #ddd;
  }
  button {
    display: block;
    margin: 20px auto;
    padding: 10px 20px;
    background: #f00;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background 0.3s;
  }
  button:hover {
    background: #c00;
  }
  </style>
  