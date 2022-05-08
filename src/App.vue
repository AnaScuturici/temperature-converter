<template>
  <div class="container">
    <Header title="Temperature converter"/>
    <Input title="temperature"/>
    <Selections :options="['°C', '°F']" />
    <Output text="output"/>
    <Button text="Convert"/>
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
};
</script>

<style>
</style>
