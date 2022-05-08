<template>
  <div class="container">
    <Header title="Temperature converter"/>
    <Input title="temperature" v-model:temperature="temperature"/>
    <Selections :options="['°C', '°F']"  v-model:fromUnit="fromUnit" v-model:toUnit="toUnit" />
    <Output v-model:output="output"/>
    <Button text="Convert" @handle-convert="handleConvert"/>
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
    Button
  },
  data() {
    return {
      temperature: "",
      fromUnit: "",
      toUnit: "",
      output: "",
    }
  },
  methods: {
    handleConvert() {
      if(this.fromUnit === "°C") {
        this.output = parseFloat(Math.round((this.temperature * 9/5) + 32));
      } else if(this.fromUnit === "°F") {
        this.output = parseFloat(Math.round((this.temperature - 32) * 5/9));
      }
      console.log(this.output);
    }
  }
};
</script>

<style>
</style>
