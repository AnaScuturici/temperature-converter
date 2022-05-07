<template>
    <div>
        <p>From:</p>
        <select v-model="selected">
            <option disabled value="">Please select one</option>
            <option v-for="(option, index) in options" :key="index" :value="option">{{option}}</option>
        </select>
        <p>To:</p>
        <select v-model="selected">
            <option disabled value="">Please select one</option>
            <option v-for="(option, index) in options" :key="index" :value="option">{{option}}</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "Selections",
    props: {
        options: String,
    },
}
</script>

<style>
</style>