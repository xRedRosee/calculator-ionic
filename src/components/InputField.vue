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
    background-color: #222428;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    height: 70px;
    border-radius: 20px;
    padding-right: 20px;
}

.input {
    font-size: 30px;
    color: white;
}
</style>