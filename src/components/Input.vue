<template>
    <div class="input-div">
        <p>Enter {{title}}:</p>
        <input type="number" :value="temperature" @input="$emit('update:temperature', $event.target.value)">
    </div>
</template>

<script>
export default {
    name: "Input",
    props: {
        type: Number,
        title: String,
        temperature: {
            type: String,
            default: '',
        },
    },
}
</script>

<style scoped>
.input-div {
    line-height: 2;
}

input {
    width: 100%;
    height: 40px;
    padding-left: 20px;
    border-color: 1px solid #5f84a2;
    cursor: pointer;
}
</style>