<template>
    <div class="output">
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
            default: 'output',
        },
    },
}
</script>

<style scoped>
.output {
    height: 200px;
    width: 250px;
    border: 1px solid #5f84a2;
    position: relative;
    margin-top: 25px;
    background: #fff;
    border-radius: 3px;
}
p {
    text-align: center;
    margin: auto;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    margin: 0;
    font-size: 17px;
    color: #031827;
}
</style>