<template>
    <div>
        <p>Enter {{title}}:</p>
        <input type="number">
    </div>
</template>

<script>
export default {
    name: "Input",
    props: {
        type: Number,
        title: String,
    },
}
</script>

<style>
</style>