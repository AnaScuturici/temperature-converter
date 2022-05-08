<template>
    <div>
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

<style>
</style>