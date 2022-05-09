<template>
  <div class="app" :class="[mode ? 'dark' : 'light']">
    <Header title="Temperature converter" :mode="mode" @toggle="toggle"/>
    <div class="container">
      <div class="form">
        <Input title="temperature" v-model:temperature="temperature" />
        <Selections
          :options="['°C', '°F']"
          v-model:fromUnit="fromUnit"
          v-model:toUnit="toUnit"
        />
        <Button text="Convert" @handle-convert="handleConvert" />
      </div>
      <Output v-model:output="output" />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Input from "./components/Input.vue";
import Selections from "./components/Selections.vue";
import Output from "./components/Output.vue";
import Button from "./components/Button.vue";

export default {
  name: "App",
  components: {
    Header,
    Input,
    Selections,
    Output,
    Button,
  },
  data() {
    return {
      temperature: "",
      fromUnit: "",
      toUnit: "",
      output: "",
      mode: "dark",
    };
  },
  methods: {
    handleConvert() {
      let result;
      if (this.temperature === "") {
        this.output = "Please enter temperature";
      } else if (
        this.fromUnit === "" ||
        this.toUnit === "" ||
        this.fromUnit === this.toUnit
      ) {
        this.output = "Please select a unit of conversion";
      } else if (this.fromUnit === "°C" && this.toUnit === "°F") {
        result = parseFloat(Math.round((this.temperature * 9) / 5 + 32));
        this.output = `${this.temperature} ${this.fromUnit} = ${result} ${this.toUnit}`;
      } else if (this.fromUnit === "°F" && this.toUnit === "°C") {
        result = parseFloat(Math.round(((this.temperature - 32) * 5) / 9));
        this.output = `${this.temperature} ${this.fromUnit} = ${result} ${this.toUnit}`;
      }
    },
    toggle() {
      this.mode = !this.mode;
    }
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;500;700&display=swap");

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  margin: 0 auto;
  font-family: "Noto Sans JP", sans-serif;
}

.app {
  min-height: 100vh;
  width: 100vw;
  background: #d6e4ee;
  color: #031827;
  transition: background 0.3s ease-in-out;
}

.dark {
  background: #031827;
  color: #f3f3f3;
}

.container {
  display: flex;
  gap: 1em;
  flex-wrap: wrap;
  justify-content: center;
  padding: 30px 0;
}

.form {
  padding: 0 1em;
}

.form > * + * {
  margin-top: 2rem;
}
</style>
