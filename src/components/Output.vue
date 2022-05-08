<template>
    <div>
        <p :value="output" @input="$emit('update:output', $event.target.value)">{{output}}</p>
    </div>
</template>

<script>
export default {
    name: "Output",
    props: {
        text: String,
        output: {
            type: String,
            default: '',
        },
    },
}
</script>

<style>
</style>