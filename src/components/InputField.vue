<template>
    <p class="input"> {{ Input }}</p>
</template>
<script>
export default {
    name: "inputField",
    props: {
        Input: {
            type: Number,
            default: 0
        }
    },
    mounted() {
        console.log(this.Input);
    }
}
</script>
<style>
.input {
    font-size: 20px;
}
</style>