<template>
    <div>
       <button @click="onClick">{{text}}</button>
    </div>
</template>

<script>
export default {
    name: "Button",
    props: {
        text: String
    },
    methods: {
        onClick() {
            this.$emit('handle-convert');
        }
    }
}
</script>

<style>
</style>