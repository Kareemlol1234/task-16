<template>
  <div class="home">
    <div class="container">
      <div class="calc">
        <div class="title">
          <h1>claculator</h1>
        </div>
        <div class="main-calc">
          <div class="row">
            <input type="text" v-model="display" readonly />
          </div>
          <div class="row">
            <div class="col">
              <button @click="clear()" class="up">AC</button>
            </div>
            <div class="col">
              <button @click="append('/')" class="up">/</button>
            </div>
            <div class="col">
              <button @click="deleteLast()" class="up">Del</button>
            </div>
          </div>
          <div class="row">
            <div class="col"><button @click="append('7')">7</button></div>
            <div class="col"><button @click="append('8')">8</button></div>
            <div class="col"><button @click="append('9')">9</button></div>
            <div class="col"><button @click="append('*')">x</button></div>
          </div>
          <div class="row">
            <div class="col"><button @click="append('4')">4</button></div>
            <div class="col"><button @click="append('5')">5</button></div>
            <div class="col"><button @click="append('6')">6</button></div>
            <div class="col"><button @click="append('-')">-</button></div>
          </div>
          <div class="row">
            <div class="col"><button @click="append('1')">1</button></div>
            <div class="col"><button @click="append('2')">2</button></div>
            <div class="col"><button @click="append('3')">3</button></div>
            <div class="col"><button @click="append('+')">+</button></div>
          </div>
          <div class="row">
            <div class="col">
              <button @click="append('0')" class="up">0</button>
            </div>
            <div class="col">
              <button @click="append('00')" class="up">00</button>
            </div>
            <div class="col">
              <button @click="calculator()" class="up">=</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "HomeView",
  data() {
    return {
      display: "",
    };
  },
  methods: {
    append(value) {
      this.display += value;
    },
    clear() {
      this.display = "";
    },
    deleteLast() {
      this.display = this.display.slice(0, -1);
    },
    calculator() {
      try {
        this.display = eval(this.display);
      } catch (e) {
        this.display = "Error";
      }
    },
  },
};
</script>
<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
.home {
  text-align: center;
}
.calc {
  background: purple;
  width: 30%;
  padding: 10px;
  margin: auto;
  border-radius: 10px;
}
button {
  width: 100%;
  margin: auto;
  margin: 20px;
  padding: 10px;
  background: white;
  color: black;
  font-size: 18px;
  border-radius: 5px;
  cursor: pointer;
}
.up {
  width: 100%;
  padding: 10px;
  background: white;
  color: black;
  font-size: 18px;
  border-radius: 5px;
  cursor: pointer;
}
.main-calc input {
  width: 90%;
  margin: auto;
  margin-bottom: 10px;
}
button:hover {
  background: #d1d0d0;
}
</style>
