<template>
    <header>
        <h1>{{title}}</h1>
    </header>
</template>

<script>
export default {
    name: "Header",
    props: {
        title: String,
    },
}
</script>

<style scoped>
header {
    text-align: center;
    padding: 50px;
    font-weight: 300;
    font-size: clamp(0.5em, calc(5vw + 0.5em), 1em);
    background: #96aec1;
}
</style>