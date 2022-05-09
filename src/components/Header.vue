<template>
  <header>
    <h1>{{ title }}</h1>
   <Toggle :mode="mode" @toggle="$emit('toggle')"/>
  </header>
</template>

<script>
import Toggle from "./Toggle.vue";

export default {
  name: "Header",
  components: {
      Toggle
  },
  props: {
    title: String,
    mode: {
      type: String,
      default: "dark",
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 50px;
  background: #96aec1;
  color: #031827;
  transition: background 0.3s ease-in-out;
}

.dark header {
  background: #02243d;
  color: #f3f3f3;
}

header h1 {
  font-weight: 500;
  font-size: clamp(2em, calc(5vw + 1em), 2em);
}
</style>