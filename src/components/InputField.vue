<template>
    <div class="field">
        <p class="input"> {{ Input }} </p>
    </div>
</template>
<script>
export default {
    name: "inputField",
    props: {
        Input: {
            type: Number,
            default: ""
        }
    }
}
</script>
<style>
.field {
    width: 90%;
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 70px;
    border: 2px solid #3880ff;
    border-radius: 20px;
}

.input {
    font-size: 30px;
    color: black;
}
</style>