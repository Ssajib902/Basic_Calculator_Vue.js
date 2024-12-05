<template>
    <div id="calculator">
      <header>
        <nav>
          <ul>
            <li><router-link to="/">Calculator</router-link></li>
            <li><router-link to="/history">History</router-link></li>
            <li><router-link to="/settings">Settings</router-link></li>
          </ul>
        </nav>
      </header>
      <div class="display">{{ current }}</div>
      <div class="buttons">
        <button v-for="btn in buttons" :key="btn" @click="handleClick(btn)">
          {{ btn }}
        </button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        current: '',
        buttons: [
          '7', '8', '9', '/',
          '4', '5', '6', '*',
          '1', '2', '3', '-',
          'C', '0', '=', '+'
        ],
      };
    },
    methods: {
      handleClick(btn) {
        if (btn === 'C') {
          this.current = '';
        } else if (btn === '=') {
          this.current = eval(this.current).toString();
        } else {
          this.current += btn;
        }
      },
    },
  };
  </script>
  
  <style scoped>
  #calculator {
    display: flex;
    padding: 20px;
    flex-direction: column;
    align-items: center;
    margin: 50px auto;
    max-width: 400px;
    height: 400px;
    border: 2px solid #ccc;
    border-radius: 10px;
    background: #f9f9f9;
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
  .display {
    width: 100%;
    height: 70px;
    margin-top: 5px;
    border: 2px solid black;
    color: black;
    font-size: 2rem;
    text-align: right;
    padding: 10px;
    box-sizing: border-box;
    border-bottom: 2px solid #ccc;
    border-radius: 10px;
  }
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
    padding: 20px;
  }
  button {
    height: 50px;
    width: 50px;
    font-size: 1.2rem;
    font-weight: bold;
    background: #f1f1f1;
    border: 1px solid #ddd;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s;
  }
  button:hover {
    background: #ddd;
  }
  button:active {
    background: #ccc;
  }
  </style>
  