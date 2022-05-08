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

<style scoped>
button {
    width: 100%;
    height: 40px;
    font-size: 19px;
    border-radius: 3px;
    background: #91aec4;
    cursor: pointer;
}
</style>