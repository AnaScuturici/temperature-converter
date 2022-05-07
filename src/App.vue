<template>
  <div class="container">
    <Header title="Temperature converter"/>
    <Input title="temperature"/>
    <Selections :options="['°C', '°F']"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Input from "./components/Input.vue";
import Selections from "./components/Selections.vue";

export default {
  name: "App",
  components: {
    Header,
    Input,
    Selections,
  }
};
</script>

<style>
</style>
