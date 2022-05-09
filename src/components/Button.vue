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
    font-size: 17px;
    border-radius: 3px;
    background: #f1b948;
    border: none;
    cursor: pointer;
}
</style>