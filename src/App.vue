<template>
  <div class="container">
    <Header title="Temperature converter"/>
    <Input title="temperature"/>
    <Selections :options="['°C', '°F']"/>
    <Output text="output"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Input from "./components/Input.vue";
import Selections from "./components/Selections.vue";
import Output from "./components/Output.vue";

export default {
  name: "App",
  components: {
    Header,
    Input,
    Selections,
    Output,
  }
};
</script>

<style>
</style>
