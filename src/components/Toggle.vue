<template>
  <div>
    <i
      @click="toggle"
      :class="[isActive ? 'fa-toggle-off' : 'fa-toggle-on', 'fa-solid']"
    ></i>
  </div>
</template>

<script>
export default {
  name: "Toggle",
  data() {
    return {
      isActive: false,
    };
  },
  props: {
    mode: {
      type: String,
      default: "dark",
    },
  },
  methods: {
    toggle() {
      this.isActive = !this.isActive;
      this.$emit('toggle');
    },
  },
};
</script>

<style scoped>
.fa-solid {
  font-size: 30px;
  color: #f1b948;
}
</style>