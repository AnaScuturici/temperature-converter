<template>
  <div class="container">
    <Header title="Temperature converter"/>
    <Input title="temperature"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Input from "./components/Input.vue";

export default {
  name: "App",
  components: {
    Header,
    Input,
  }
};
</script>

<style>
</style>
