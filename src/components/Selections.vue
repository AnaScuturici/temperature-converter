<template>
  <div class="selections">
    <p>From:</p>
    <select
      :value="fromUnit"
      @change="$emit('update:fromUnit', $event.target.value)"
    >
      <option disabled value="">Please select one</option>
      <option v-for="(option, index) in options" :key="index">
        {{ option }}
      </option>
    </select>
    <p>To:</p>
    <select
      :value="toUnit"
      @change="$emit('update:toUnit', $event.target.value)"
    >
      <option disabled value="">Please select one</option>
      <option v-for="(option, index) in options" :key="index">
        {{ option }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Selections",
  props: {
    options: {
      type: Array,
      default: [],
    },
    fromUnit: {
      type: String,
      default: "",
    },
    toUnit: {
      type: String,
      default: "",
    },
  },
  methods: {
    handleSelect() {
      this.$emit("select");
    },
  },
};
</script>

<style scoped>
.selections {
  display: flex;
  gap: 1em;
  flex-wrap: wrap;
  justify-content: center;
}

select {
    height: 40px;
    padding-left: 10px;
    cursor: pointer;
}
</style>